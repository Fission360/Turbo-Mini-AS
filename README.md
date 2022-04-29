# Turbo-Mini-AS (Beta)
![IMG_4189](https://user-images.githubusercontent.com/93737816/165895620-29b7efa9-3de0-40d0-9382-efdba18dc3aa.JPG)

I love my V0.1 to bits. With my current setup, my part cooling is the limiting factor, and which was preventing me from printing PLA/PETG/ABS just a *little* faster. If you're reading this, you may also be dissatisfied with the V0.1's part cooling performance. Enter Turbo Mini AfterSherpa.

**Note:** this mod was made to work with a hinged tophat of sorts
This design was originally inspired by Vez3D (https://www.youtube.com/watch?v=E3kBau82SwU), and I would say that you need to watch for some wiring and pinout stuff. I started with KurioHonoo's Mini AfterSherpa (https://github.com/KurioHonoo/Mini-AfterSherpa/blob/main/README.md) and replaced the area for the 3010 fans with an internal ducting system, which directs air from a 7040 brushless blower fan. 

# BOM
  - Assembled Sherpa Mini (use an M3 bolt instead of a thumbscrew): https://github.com/Annex-Engineering/Sherpa_Mini-Extruder
  - CPAP tubing: https://www.amazon.com/SnugellTM-Universal-Premium-Compatible-Respironics/dp/B08C6XBCLY?keywords=ResMed%2BSlimLine%2BCPAP%2BTubing%2B15mm%2Bx%2B2M%2B(1)%2Bby%2BSlim%2BLine&qid=1647318212&sr=8-3&linkCode=sl1&tag=vez3d-20&linkId=8082d875c1563bcbad274bb9564164fe&language=en_US&ref_=as_li_ss_tl&th=1
  - Blower fan: https://www.aliexpress.com/item/32980201709.html?aff_fcid=2de385b8aabc470c8ee7223369581bb9-1651215161001-02224-_AEsHxz&tt=CPS_NORMAL&aff_fsk=_AEsHxz&aff_platform=shareComponent-detail&sk=_AEsHxz&aff_trace_key=2de385b8aabc470c8ee7223369581bb9-1651215161001-02224-_AEsHxz&terminal_id=78206e80840c4585a8b35c500394c395&afSmartRedirect=y OR https://www.aliexpress.com/item/4000959990877.html?aff_fcid=1c4c00ce8283451584df39f5813133f5-1651215163111-00767-_AAzQAX&tt=CPS_NORMAL&aff_fsk=_AAzQAX&aff_platform=shareComponent-detail&sk=_AAzQAX&aff_trace_key=1c4c00ce8283451584df39f5813133f5-1651215163111-00767-_AAzQAX&terminal_id=78206e80840c4585a8b35c500394c395&afSmartRedirect=y
  - Low-pass filter
    - 1x 10K resistor (link for assorted kit): https://www.amazon.com/gp/product/B07L851T3V/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1
    - 1x 1uF capacitor (link for assorted kit): https://www.amazon.com/dp/B07KC99W2K?psc=1&ref=ppx_yo2ov_dt_b_product_details
    - 1x 1-pin female dupont connector (link for assorted kit): https://www.amazon.com/gp/product/B07CVYPDGS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1
    - 1x 2.54mm JST-XH 2-pin and 1x 2.54mm JST-XH 3-pin (link for assorted kit): https://www.amazon.com/gp/product/B0731NHS9R/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1
    - Wire
    - Solder and soldering iron
  - 


In your config, change "fan" to the below settings

<img width="216" alt="Screen Shot 2022-04-28 at 11 58 19 PM" src="https://user-images.githubusercontent.com/93737816/165898117-19b03a1c-e4a8-4704-80c5-b39b65fa33c3.png">

For best results
