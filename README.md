# multichannel-gnss
Advanced navigation GPS based on GNSS-SDR and coherent multichannel SDR receivers

# motivation
The GPS applications become ubiquitous but in the consumer GPS market we are still using a technology which casts us back 15-20 years.

Majority of the consumer GPS devices still rely only on coarse acquisition code transmitted on L1 (1575.42MHz), because of the several factors which affect the propagation of the signal trough ionosphere the accuracy of the civilian GPS receivers is limited to around 3m.

There are several more expensive solutions which exists on the market and used by surveyors. These units are capable of centimeter accuracy but require a base station with the known coordinates within a close proximity to a “rover” a measuring unit to compensate for the atmospheric distortions.

There is an open source implementation exists which allows to use certain GPS receivers which expose phase frequency of the GPS signal (UBLOX 6T, NAVSPARK RAW and alike) and SDRs to accommodate the base station and the rover requirements, still the solution is cumbersome and sometime require an extensive time to lock on to an accurate position solution.

The military equipment solves this problem by using two harmonically synched frequencies the L1 and L2 (1227.60 MHz). The L2 frequency is encrypted and is not available for the civilian use.

Understanding the increasing need for precise navigation solutions fueled by the upcoming market of the Unmanned Aerial Systems and Unmanned Ground Vehicles the US government is engaged in a broad modernization effort of the existing GPS constellation of satellites to include number of additional signal frequencies available to civil use which are broadcasted on other than L1 frequency. One of the first additional signals which was added is transmitted on the L2 (1227.6 MHz) frequency. The L2C signal frequency was activated in April 2014 and suppose to reach full operating capacity sometime in 2017.

Having two signal transmitted from the same satellite on two different frequencies allows to measure and compensate for an ionospheric delay, vastly improving the accuracy calculated by a capable GPS receiver.

Unfortunately at this stage there are no consumer priced, readily available GPS units which could accommodate L2C signal.

An attempt is made to use coherent multichannel SDR receivers (rtl-sdr and hackrf) as a Global Navigation Satellite System RF front end for GNSS-SDR software.

The builds located in ./gnss-sdr-binaries include generic non SIMD CPU dependent binaries with Osmosdr_Signal_Source support

Additional information related to a coherent rtl-sdr receivers configuration driven by Si5351 is located in ./documentation
