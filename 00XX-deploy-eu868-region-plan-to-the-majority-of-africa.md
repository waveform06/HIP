# HIP XX: Deploy EU868 region plan to the majority of Africa
* Author: [Adrian Clint](https://github.com/waveform06) and [Helium Foundation](https://github.com/dewi-alliance) 
* Start Date: 2023-09-22
* Category: Technical
* Original HIP PR: [#789](https://github.com/helium/HIP/pull/789)
* Tracking Issue:
* Vote Requirements: veIOT Holders

## Summary



The Helium Foundation recommends that the community provisionally sets the currently unspecified and EU433 only/primary countries in the Africa region to the EU868 frequency plan, to match with what we understand from local regulatory authorities like the Africa Telecoms Union (ATU) and local deployers have defined as the future LoRaWAN regional frequency plan. The LoRa Alliance does not currently specify regional parameters for these countries, or has EU433 as an only/primary frequency plan, so this would be an addition that the Helium Foundation is proposing for Helium network specific devices. The LoRa Alliance has so far only been successful with a country-by-country, or bottom up, approach to allocation of frequencies.

The Foundation proposes, with a few exceptions:

* All Africa region countries currently set to an “Unknown” LoRaWAN regional frequency parameter are set to ETSI [EN300.220-2] standard. Region code EU868 on the Helium network.
* All Africa region countries currently primarily set to EU433 as the default LoRaWAN regional frequency parameter are set to EU868 on the Helium network.
* All Africa region countries with EU433 or an 800MHz based LoRaWAN regional frequency parameter are set to EU868 on the Helium network.
* We approach and communicate with all Telecoms Regulatory Authorities in these countries and confirm Helium provisionally complies with the EU868 regional parameter recommendation from the Africa Telecoms Union, and ask for confirmation that provisional operation is not disallowed in this provisional configuration.
* The Helium Foundation presents this change and approach to the LoRa Alliance Regulations and Regional Parameters Working Groups.

## Motivation


Africa, as a continent, is lagging behind in the regulation of LoRaWAN frequency plans for each country, and additionally haven't attempted to harmonize frequency plans that are in use by countries that have a defined LoRaWAN frequency plan. The local regulatory authorities have not prioritized frequency plan selection as other efforts in 5G have taken precedence.

The Helium network is being approached by organizations that want to deploy compatible infrastructure in Africa that do not have a frequency plan or have one that is legacy and is not recommended for future use - EU433. Unfortunately, the legal LoRaWAN frequency varies from country to country within the continent. Even rapidly growing IT-focused countries are having trouble defining the exact legal spectrum on which to operate, unless supported by other organizations or Unions.

The near term goal is to establish EU868 as a provisional regulation allowing Helium to deploy EU868 Hotspots across the African continent. By making this provisional change to the Helium network, we are able to initiate the process to formally change the LoRa Alliance's RP2-1.0.5 LoRaWAN Regional Parameters document - allowing Helium to deploy EU868 across Africa.  EU868 is already used in the largest African countries, including South Africa, Nigeria, Egypt and Kenya but most countries in Africa do not have applicable any regulations and have no assigned usable frequency plan specifically for LoRaWAN.  The ETSI [EN300.220-2] standard 868 band is the most likely eventual winner as a de facto standard for IoT devices in most of the world with no regulations, especially in ITU Region 1 (EMEA). 


![itu1 map](images/itu1.png)


Pic 1: The ITU Region 1 is shown in the map above. From ITU Radio Regulations 2020

The trigger countries for this HIP are Malawi, Liberia, The Democratic Republic Congo, The Republic of Congo, and Ghana who the Foundation are working with on the ground through the OPEN team to establish local LoRaWAN connectivity on EU868 in these countries.

This frequency selection proposed here would be subject to future government or regulatory updates, or an update from the LoRa Alliance. Since this is a local initiative, it's assumed that Hotspot owners are going to deploy Hotspots on their own behalf and not on behalf of the Foundation.  So this guidance is based on our understanding of the local rules through conversations with the regulators and the community. Ultimately, Hotspot owners are the ones who are assuming the risk of deployment, assertion, and ongoing operation. If a Hotspot owner has specific questions or concerns, they should seek current local regulatory or legal advice.

The LoRa Alliance has a country by country bottom up approach to allocation of frequencies and has not successfuly managed to push for harmonization of a frequency plan to a region as a top down approach. There is no specific LoRa Alliance Africa regional task force dedicated for any approach region wide like there is for Australia-NZ or Latin-America.

Organizations such as ECOWAS - Competition Authority of the Economic Community of West African States and CRASA - Communications Regulators' Association of Southern Africa are responsible for resolving spectrum issues in general and IoT specifically.  But critical regulatory work in many African countries lags behind other technologies and thus, most don't have LoRaWAN frequency plans which hinders technical IoT development and network deployments.


---

A fundamental first step is needed to resolve the regulatory issues and provide any LoRaWAN deploying organization with regulatory assistance.  Without a clear mandate to use a region wide frequency, other LoRaWAN service providers and device makers cannot determine which hardware to build or use..  

The 2024 goal would be to have the EU868 region for Africa map to include the countries, islands and UK/France Territories as shown below.

![Africa 2024](images/africa2024v2.png)


Pic 2: The countries to be allocated EU868 by this HIP


## 
**Stakeholders**



* Prospective and current deployers of LoRaWAN Gateways and Sensors in each of the countries specified in this HIP.
    * Eg , [One Planet Education Network](https://www.oneplaneteducation.com/) (OPEN) 
* The LoRaWAN Alliance Regulatory and Regional Parameters Working Groups (Foundation has been in contact)
* The African Telecoms Union (ATU) (Foundation has been in contact)
* The country’s Regulatory Telecoms Authority in each of the countries in Tables 1,2 & 3
* African Telecoms and Commercial and Economic organizations such as:
    * Commission of the Economic Community of West African States [ECOWAS](https://ecowas.int/ecowas-member-states-adopt-common-positions-on-agenda-items-of-the-world-radiocommunications-conference-2023-wrc-23/) (Foundation has been in contact)
    * Communications Regulators' Association of Southern Africa ([CRASA](https://www.crasa.org/))
    * Arab Spectrum Management Group ([ASMG](https://www.itu.int/en/ITU-R/terrestrial/broadcast/ASMG/Pages/default.aspx)) 
    * Others are [https://en.wikipedia.org/wiki/Regional_Economic_Communities](https://en.wikipedia.org/wiki/Regional_Economic_Communities)
* Other Public or Private LoRaWAN networks who may want to deploy the same regional frequency plan we are proposing or another one.  
* Specifically any hotspot owner in Algeria or operator of sensors on the Helium network in Algeria. Though if this HIP is not approved the region change in Algeria will still be implemented.

We will attempt to contact all Unions, Regulatory Telecoms Authorities and Commercial and Economic organizations where regional frequency changes are proposed.


## 
**Detailed Explanation**

Proposed regional frequency plan changes from the LoRaWAN Alliance's RP2-1.0.4 LoRaWAN Regional Parameters document will be deployed in the regions.csv file and the appropriate  .geojson files to match the new changes in the tables below.

The most recent github issue for this is [https://github.com/dewi-alliance/hplans/issues/51](https://github.com/dewi-alliance/hplans/issues/51) 

But will require updates or modification depending on the outcome of this HIP.

The full proposed regional frequency plan changes are detailed in this set of tables:

![tables 1-5](images/tables1-5v2.png)


_Note: The countries marked with a * are members of CRASA and frequency harmonization amongst members is a goal of this organization._

**Table 1**: Countries with no defined regional frequency plan (Unknown) will be set to EU868 - ATU discussed any countries wanting to define a regional frequency and looking for a recommendation for one from the ATU will have EU868 proposed


*Note: Eritrea and South Sudan do not appear to be or have been members of the ATU or CRASA - TBC. Some other countries need to have membership status confirmed*

**Table 2**: Countries with the EU433 plan defined will be set to EU868 - as per reasoning for Table 1 and because the LoRaWAN Alliance recommend no new EU433 installations or support. Helium HIP19 has not approved any EU433 hotspots so far.

**Table 3**: Countries with EU433 and any 800MHz plan defined will be set to EU868 - as per reasoning for Table 1 and that LoRaWAN Alliance recommends no new EU433 installations or support. \
	This would support [hplans github issue 27](https://github.com/dewi-alliance/hplans/issues/27)

**Table 4**:The LoRaWAN Alliance has updated the regional parameters for Algeria from AS923-3 to EU868 and we will follow their direction. Similarly Mauritius and Morocco have been updated from EU433/800MHz to EU868.

**Table 5**: Saint Helena and its associated islands has been added as a proposal in this HIP though officially outside the Africa Region but is adjacent to other African islands and is a UK (EU868) Overseas Territory. It can be assumed that it would also be EU868 as African Islands that are French Overseas Territories are defined as EU868. And it exists within ITU Zone 1.


---

Other countries such as Uganda (AS923-1), Tanzania (AS923-1) and Niger (IN865) have specifications other than EU868. Lesotho, Libya, Sierra Leone and Sudan have frequency spectrum specifications that in our opinion need further review before we would deploy EU868. It would be expected that over time all these countries harmonize with the proposed region plan of the ATU for EU868, this HIP does not describe a current attempt to change them, but proposes to add EU868 to the list of their allowable regional frequencies in the Helium regions.csv file. 


The Southern African Development Community (SADC)’s regulatory arm - the Communications Regulators' Association of Southern Africa (CRASA) has a [frequency allocation plan](https://www.crasa.org/post-articles/sadc-radio-frequency-spectrum-allocation-plan-rfsap) common to all member countries. And members are urged to follow this “In order to achieve significant harmonization… as far as is practically possible.”

![table 6](images/table6.png)


Table 6: List of SADC Member countries


## 
**Drawbacks and Risks**


1. Is deploying EU868 to the remaining Unknown, and EU433 defined countries a step too far?.
    1. Should we implement this change to only countries that we have local relationships with and deployers encouraging implementation of EU868?
    2. Should we only deploy to the specified countries in the different Tables 1, 2 and/or 3? (Table 4 will be deployed if HIP does not pass)
    3. Should we implement this change to only ATU member countries?
    4. Should we implement this change to only countries with an 800MHz regional plan allowed?
    
2. The problems that could occur if we implement EU868 and the country implements another regional plan are.

	If the country implements another 800MHz based plan, eg IN865
* Hotspot vendors would have allow their hotspots to be changed to this plan
* Helium would have to update the hplans repository to support this new plan and release configurations to the hotspot to operate at this new plan
* Sensor owners would need to reconfigure the Sensors from EU868 to the new plan


	If the country implements a non 800MHz based plan, eg AS923, AU915, CN470
* Hotspot vendors would have allow their hotspots to be changed to this plan
* Helium would have to update the hplans repository to support this new plan and release configurations to the hotspot to operate at this new plan
* Hotspot owners would need to replace the LoRaWAN Concentrator with a 400/900MHz based item if the hotspot vendor technically and support wise allows this change and these are available.
* Sensor owners would need to reconfigure the Sensors from EU868 to the new plan if they can operate on the 400/900 MHz plan, or replace them with ones that can.

## 
**Rationale and Alternatives**


The Foundation is working on continuing a dialogue with the African Telecom Union (ATU) which establishes regulatory frameworks for the entire African continent.  Our current operating assumption is that the ATU does not have LoRaWAN or IoT on its priority roadmap of list of actions as 5G regulation has been the priority recently.  If we can get IoT regulation on the priority list, we can work to eventually establish a single regulation for the entire African continent, the same way that WiFi and cell phones are regulated.

At the LoRa Alliance Regulatory Working Group (Not to be confused with the Regional Parameters Working Group) meetings, the traditional approach with all countries has been bottom up. But this proposal is to take a top down approach. The LoRa Alliance Regulatory WG gets regular updates on a quarterly LoRaWAN Spectrum Report. This focus is entirely on individual countries though, rather than the region-wide framework which leads to regulations. 

Telecoms Standard ERC 70-03 drives most regulations world-wide including Africa.  The idea of a "Provisional" or temporary regulation for Research & Development was mentioned in discussions  Our current understanding is that after discussion with the International Telecommunication Union (ITU) the ATU supports [ERC Recommendation 70-03](https://docdb.cept.org/download/4358)  for [ITU region 1](https://en.wikipedia.org/wiki/ITU_Region) (EMEA) and we want to assist the ATU in decreasing the deployment delay in implementation in Africa for the smaller countries.So our take will be that these region parameter changes are "provisional".

The ITU and ATU are recommending a single SRD standard for all African countries based on ERC rec 70-03 and ETSI EN 300 220.  This means that LoRaWAN's EU868 will become the standard for all countries in Africa...eventually. But as the ATU points out however, the countries in Africa are sovereign nations and must create their own regulations and do not need to implement ITU or ATU recommendations.

Out of 54 countries in Africa only 18 have adopted SRD regulations, which leaves about 36 unregulated countries.  However 51 African countries are members of the Africa Telecom Union (ATU) and will most likely adopt the ATU's African Spectrum Allocation Plan (AfriSAP) recommendations eventually.

The ATU’s advice to Helium Foundation is to approach regulators and point them towards Helium's compliance with the standard listed in ATU's African Spectrum Allocation Plan (AfriSAP) [https://atuuat.africa/african-spectrum-allocation-plan-afrisap/](https://atuuat.africa/african-spectrum-allocation-plan-afrisap/) where page 61 identifies 862 to 890 MHz as the frequency to use.  

The Foundation will be working with local partners where possible such as OPEN who can do a lot of the driving the local telecoms regulatory authorities to make decisions about proposed frequency implementation. OPEN has backing from SeeedStudio and RAKWireless amongst others to implement EU868 in their countries of operation.

We can then devise a letter from a government official granting Helium provisional permission to use LoRaWAN within that range on the EU868 regional plan.  The ATU has agreed to help us draft a template letter we can reuse for any country lacking SRD regulations in Africa.  

Slightly different communications will be deployed for those countries with EU433 as the current or primary regional plan.

This top down strategy for a whole region should simplify and speed up the permissions process with any individual country.  In the past the back and forth discussion to explain LoRaWAN, the Helium Foundation, our devices and exactly what radio spectrum permissions we are requesting has often taken six months or longer and sometimes over a 100 email exchanges.  This new approach incorporates months of research and knowledge about SRD history and is therefore a better foundation to begin negotiations between an organization local in the country and the local regulatory authority or government

**Why doesn't Helium wait for the LoRaWAN Alliance to set the frequency?**

Our approach is significantly different from the LoRa Alliance. The Alliance works with individual African countries on a case-by-case basis and has not contacted the ATU to discuss an overall harmonious Africa plan. They've admitted progress has been slow, especially for the smaller countries and it could literally take a decade before all African countries have finalized regulations.  The Helium plan is to drastically shorten that time with a provisional approval by pushing a suggested regional plan rather than waiting to approve a regional plan for one country at a time.

The African Telecom Union suggests we approach regulators and point them towards Helium's existing compliance with the standard listed in the ATU's African Spectrum Allocation Plan (AfriSAP) on page 61 for 862 to 890 Mhz.  We can then request a letter from a government official granting Helium provisional permission to use LoRaWAN within that range. 

The LoRaWAN Alliance Regional Parameters Working Group is supportive of our efforts to speed up deployment and standardization of regional regulation in the Africa Region. 

If we do not take the initiative then it will take many years for all countries in Africa to have defined regional frequency plans for LoRaWAN to operate on and maybe several more before the whole region/continent is harmonized as Europe or North America is.

The more upfront work the Foundation can do on this then the quicker companies with LoRaWAN use cases that want to deploy in Africa can implement and add value to the Helium ecosystem

**Why not use EU433?**

Helium [does not support EU433 ](https://github.com/dewi-alliance/hplans/issues/49)and has no plans to ever support EU433 or approve EU433 hardware given it is a deprecated legacy band. Countries with only EU433 support should consider regulations to support the 800 or 900 Mhz SRD bands.

The 433 MHz SRD regulations limit 433 to very, very low power limits (12dBm in ITU Region 1) thus making EU433 not useful for Helium. Semtec has strongly advised Helium to not support EU433.

We will remove any and all references to EU433 in hplans, such as Gambia as the first regional code for each country..We will retain EU433 in the "Region2" category. After moving African countries to EU868 the only countries remaining with EU433 as the only valid channel plans are Azerbaijan and Uzbekistan - which will thus have no Helium support.

**Why not use AS923?**

Only 2 African countries have a 900MHz based frequency defined as the default band, Tanzania and Uganda, Algeria has been moved from AS923 to EU868 by the LoRa Alliance.

Ten times this number have an 800MHz based frequency plan approved. The larger countries in Africa are already approved for EU868 including South Africa, Nigeria, Egypt and Kenya.

The African Telecoms Union [African Spectrum Allocation Plan](https://atuuat.africa/african-spectrum-allocation-plan-afrisap/) (AfriSAP) on page 61 shows an 800MHz not 900MHz proposed band “The band (863 – 870 MHz) is used for IoT applications, ETSI EN 300 220”

The Southern African Development Community has 16 member countries, only 1 of which has chosen AS923, and 7 have chosen EU868 as possible region plans. 

The Africa Telecom Union (ATU) in a meeting with Helium and Open confirmed Helium's original research and theory which is that the ATU is recommending a single SRD (Short Range Devices) standard for all African countries based on CEPT ERC rec 70-03 and ETSI EN 300 220.  This means that LoRaWAN's EU868 region should eventually become the standard for all countries in Africa.

**Why not use IN865, AU915 or US915?**

IN865 uses the same hardware as EU868 and any country regulator configuration changes to use this frequency would not cause much implementation problems. Niger is the only African country deploying this regional parameter at the moment, though others have it as a country option.

AU915 and US915 are static not dynamic regional parameters and dont have the unique configurable capability that EU868 and AS923 have for future country configuration support, plus these are currently not primary supported regional parameters in the Africa physical region.

**What about EU868-2?**

This is a possible new regional plan to support Saudi Arabia, as the default required sensor join frequencies of EU868 are subject to interference. This would shift the default join and operational frequencies by an offset. If a country decides to implement EN868-2 then this change will be implemented by Helium as the change from EU868 to EU868-2 will be. The countries bordering Saudi Arabia are Egypt (EU868), Sudan, Eritrea, Djibouti and Somalia (EU868/EU433/AS923-3).

**Why not wait until the outcomes of the next [ITU World Radiocommunication Conference 2023](https://www.itu.int/wrc-23/) (WRC-23)**

The LoRaWAN Alliance have informed us there is no applicable agenda items discussing LoRaWAN regional plans at this conference. 

**Concerns about deploying redundant hardware**

If there are concerns for a specific country that an “unknown” or only “EU433” country could move to regulate an 900MHz region rather than an 800MHz one at some point. Then it is suggested that any solution deployer purchase Helium Hotspots that are confirmed from the vendor can (a) Operate at 900MHz based regions as well as 800MHz and (b) support the replacement of the LoRaWAN concentrator with a 900MHz based unit.


## 
**Unresolved Questions**

Q1: Do we include the British Overseas Territory of Saint Helena, Ascension, and Tristan da Cunha in this HIP too? 


*A1: These are islands west of Africa that are UK (which is EU868) Territories. France’s African territories of Reunion and Mayotte are already EU868.*

Q2: What transmit power do we use?


*A2: We will set all countries to use the default tx power of EU868. In the ETSI [EN300.220-2] standard the Max EIRP is considered to be +16 dBm.*


*Countries currently or eventually specifying higher or lower EU868 tx power could be allocated a different region code within our _hplans_ repository with a specific tx power different to the default. EG EU868-1A*

Q3: What sequence do we contact the country's telecoms regulatory authorities?


*A3: We have a priority list with the countries that Open are attempting to deploy with and they have support from some lobbying organizations within those countries. We can put a request out to the community for organizations wishing to deploy to other countries on the list as step 2 and then do a broad contact with the rest and work first with those fastest to respond.*


*This would be an ongoing active HIP for the next few years with no deadline unless a decision or vote is taken to halt proactive provisional work. Success Stages can be updated within this HIP after feedback.*

The LoRa alliance may request that an Africa Task Force be created to gain support from other Alliance members. We do not yet know if this will be requested or required as a result of this HIP.

As deployment of sensors often requires downlink transmissions as well as uplink transmissions Helium hotspots will be able to transmit on EU868 frequencies, sometimes in countries where provisional EU868 transmission has not yet been approved. The Foundation will make it clear in the regional frequency documentation that these are provisional configurations and local telecoms approval must be sought to operate legally.


*We can do this in on the docs site, in github and we can contact Hotspot manufacturers and resellers to be aware of this, how else could the Foundation do this better.*


## 
**Deployment Impact**

Helium uses the configuration files at [https://github.com/dewi-alliance/hplans](https://github.com/dewi-alliance/hplans) to define the regional frequency plans for each country. hplans is a geojson representation of the LoRaWAN regional parameter channel plans. It is based on the LoRa Alliance's RP2-1.0.4 LoRaWAN Regional Parameters, as well as the Helium Network's country definitions.


The geojson does not contain the channel plan and spectrum definitions; it only contains the geographic regions they apply to.



* The regions.csv file is the table of frequencies and the .geojson files visually show the countries that each region code  is applied to.
* The current file status is the configuration to be applied at the next release
* The last release was on the [2nd of June 2023](https://github.com/helium/lorawan-h3/releases) and uses this set of [regional frequency parameters and plans](https://github.com/dewi-alliance/hplans/tree/e2a3a57a86c71e05064037576b3bc5f910ef5267)
* [Lw-generator](https://github.com/helium/lorawan-h3/tree/region_params_2023.06.02) generates uber h3 files for helium to use from the geojson files

There are a small number of hotspots in Algeria Switching from AS923 to EU868 and means their hardware is now obsolete, unless the hotspots can have their LoRaWAN Concentrator replaced,

**Documentation/knowledge updates**



* [https://docs.helium.com/iot/lorawan-region-plans](https://docs.helium.com/iot/lorawan-region-plans) will be updated
    * A note will be added to each country affected, to a copy of this HIP and the decision and suitable processes for local regulatory authorities to use the frequency.
    * Countries not yet confirmed as EU868 by the LoRa Alliance will be noted as provisional proposed
    * Current status updates with countries viewing the EU868 proposal will be noted on this page or subpage
* [https://github.com/dewi-alliance/hplans](https://github.com/dewi-alliance/hplans) will match the docs site

Any countries authorities confirming they do not want to provisionally or actively deploy EU868 will be returned using the above processes to the LoRaWAN frequency plan definition in the latest LoRa Alliance Regional Parameters documentation. And any known deployers in that country in contact with the Foundation will be notified of the return to Alliance definitions..

**Success Metrics**

**Phase 1 - before or during 2024 Q1**

Malawi, Liberia, The Democratic Republic Congo, The Republic of Congo and Ghana who the Foundation are working with through the OPEN team have a fixed or provisional EU868 frequency assigned by local regulators.

**Phase 2 - before 2024 Q3**

That all countries telecoms regulators in Tables 1-5 are contacted by the Helium Foundation proposing the provisional allowance of the EU868 as a regional LoRaWAN standard and a response status table is updated on the Helium DOCs pages.

Regular updates on the regional EU868 take up will be provided on the Community Calls.

A further success metric will be the willingness of other LoRaWAN network operators to engage with and support this proposal for their own deployments

**References**



* LoRaWAN Alliance's [RP2-1.0.4 LoRaWAN Regional Parameters](https://resources.lora-alliance.org/technical-specifications/rp002-1-0-4-regional-parameters)
* ITU [Radio Regulations 2020](https://www.itu.int/hub/publication/r-reg-rr-2020/)
* ATU's [African Spectrum Allocation Plan](https://atuuat.africa/african-spectrum-allocation-plan-afrisap/) (AfriSAP) See page 61 for 862 to 890 Mhz
* CRASA’s [Radio Frequency Spectrum Allocation Plan](https://www.crasa.org/post-articles/sadc-radio-frequency-spectrum-allocation-plan-rfsap) (RFSAP)
* CEP [ERC Recommendation 70-03](https://docdb.cept.org/download/4358) Relating to the use of Short Range Devices (SRD)
* ETSI [EN 300 220-2](https://www.etsi.org/deliver/etsi_en/300200_300299/30022002/03.02.01_60/en_30022002v030201p.pdf) V3.2.1 (2018-06) Short Range Devices (SRD) operating in the frequency range 25 MHz to 1 000 MHz
* ITU Region 1. Shown below, includes the islands of St Helens, Ascension, Cunha and Gough


![itu1](images/itu1.png)

