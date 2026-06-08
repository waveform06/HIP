# HIP 145: Demand Sampling

- Authors: [@zer0tweets](https://twitter.com/zer0tweets), [@jhiller](https://twitter.com/jhiller), [@madninja](https://twitter.com/madninja)
- Start Date: 2025-06-23
- Category: Economic, Technical
- Original HIP PR: [#1171](https://github.com/helium/HIP/pull/1171)
- Tracking Issue: [#1174](https://github.com/helium/HIP/issues/1174)
- Voting Requirements: veHNT holders

---

## Summary

This HIP proposes a new method for estimating Hotspot utility prior to MNO offload, referred to as *Demand Sampling*. (In earlier versions of this HIP, this method was referred to as *Utility Probing*.) This will be rolled out initially in the United States and eventually expanded to include Helium Mobile Hotspots worldwide.

Under this system, eligible (greenfield) Helium Mobile Hotspots will continuously broadcast Mobile Network Operator (MNO) compliant SSIDs. Subscribers from participating MNOs will attempt to connect, but their connections may be intentionally denied by Nova. Alternatively, the Hotspots may transfer Unrewarded Data for a limited period of time, before they have been selected for MNO offload. The purpose of this process is to estimate how many unique subscriber devices would connect to the Hotspot if selected for offload, which serves as a proxy for real-world utility. This data will be used to influence PoC rewards, and to inform the selection process for MNO offload.

Regions such as Mexico, where subscriber offload density is low, will continue earning PoC rewards under the current model and will switch later once subscriber density from Telefónica offload reaches adequate levels in select regions.

---

## Motivation

Key goals for making this change:

- Make it easier to identify which Hotspots are useful and should be included in the carrier offload program.
- Improve reward distribution by focusing on Hotspots that truly serve users.
- Move away from relying on static data, such as foot traffic estimates from oracles.

Currently, PoC rewards depend mostly on a Hotspot’s location, but ignore critical factors such as proper antenna placement (e.g., not blocked by walls) or installation height, which affects coverage quality. As a result, some poorly performing Hotspots still earn rewards, while well-placed ones may receive fewer rewards than they deserve.

In the U.S., Helium offloads mobile data from two of the top three major carriers, giving access to a large pool of around 250 million subscribers. By counting how many devices connect in the Demand Sampling process, we can obtain a strong, real-world signal of each Hotspot’s value.

This approach not only provides a more accurate utility signal than GPS-based location, but also eliminates the need for CDR verification.

---

## Stakeholders

This HIP primarily affects Helium Hotspot deployers in the United States.

---

## Detailed Explanation

- Hotspots already serving MNO subscribers and those outside the U.S. (e.g., in Mexico under Telefónica) are excluded from Demand Sampling for activated offload carriers. Connections for activated carriers will be counted and rewarded following the existing PoC reward algorithm.
- Greenfield Helium Hotspots (excluding self-serve brownfield Networks and Helium Plus Hotspots) will be remotely updated to broadcast MNO-compliant SSIDs.
- Demand Sampling will involve:
  - MNO subscriber devices will attempt to connect, but Nova will deny the connections before they are passed along to carriers.
  - Alternatively, Hotspots may transfer Unrewarded Data during periods of Demand Sampling.
  - The goal is to count the demand for data transfer at the Hotspot location and gather fronthaul performance metrics.
  - The process of Demand Sampling will not negatively impact the user experience for MNO subscribers.
- The number of connection attempts, or the amount of data transferred, during a 24-hour period (aligned with the rewards epoch) will help determine PoC rewards and potential offload utility for that period.

Currently, PoC rewards are based mostly on how many hexes a Hotspot covers and a multiplier based on the hex’s location quality. Under this new system, rewards will instead be based on how many connection attempts the Hotspot receives during the Sampling period, or how much data is transferred. Demand Sampling metrics will aid MNOs in their decision to offload to a particular Hotspot. 

Current stats show a median of approximately 50 unique MNO subscriber connections per 24 hours across all active Hotspots. The bottom 20% see about 5 connections or fewer in that period. [Detailed breakdown available here](https://docs.google.com/spreadsheets/d/15CcQQVw4ps5DZHcGNeha3w0mAU-r34qn56Ik52FRcJU/edit?usp=sharing).

To ensure fairness and prevent outliers from skewing results, a cap of 200 connections per day is proposed to achieve the maximum PoC points. Hotspots that receive between 0 and 200 connection attempts will earn PoC rewards based on a [formula shown in this spreadsheet](https://docs.google.com/spreadsheets/d/1Iu-jxdQFp8yoi1QjtSuNoJ3StjOL70h8iDPpzNSpyJ4/edit?usp=sharing). The allocation of PoC rewards may be revisited in future HIPs.

Simultaneously, CDR requirements for U.S. Hotspots will be deprecated. Data gathered from Demand Sampling (user counts and fronthaul metrics) will also accelerate the onboarding of Hotspots into the MNO offload program.

---

## Drawbacks

This change introduces the potential for new forms of gaming. That is, without CDRs, it becomes possible to fake results—for example, by placing multiple AT&T phones near a group of Hotspots to simulate activity, even if those Hotspots are poorly located or spoofed using RF techniques.

---

## Implementation

The implementation will be completed by Nova in two stages:

1. **Initial Rollout:** Run Demand Sampling for 30 days to collect data and resolve any bugs or edge cases related to Sampling behavior.
2. **Activation:** After the 30-day period, if no major changes to the approved algorithm are needed, user metrics from Demand Sampling will begin to affect PoC rewards, and may be made available to MNOs for use in their selection process.

---

## Success Metrics

The key success indicator will be a reduction in the percentage of Hotspots located in high footfall areas that serve few or no users and merely collect PoC rewards.
