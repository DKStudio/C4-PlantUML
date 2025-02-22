# Layout Options

PlantUML uses [Graphviz](https://www.graphviz.org/) for his graph visualization. Thus the rendering itself is done automatically for you - that it one of the biggest advantages of using PlantUML.

...and also sometimes one of the biggest disadvantages, if the rendering is not what the user intended.

For this reason, C4-PlantUML also comes with some layout options.

## LAYOUT_TOP_DOWN() or LAYOUT_LEFT_RIGHT()

With the two macros `LAYOUT_TOP_DOWN()` and `LAYOUT_LEFT_RIGHT()` it is possible to easily change the flow visualization of the diagram. `LAYOUT_TOP_DOWN()` is the default.

```csharp
@startuml LAYOUT_TOP_DOWN Sample
!includeurl https://raw.githubusercontent.com/DKStudio/C4-PlantUML/master/C4_Container.puml

/' Not needed because this is the default '/
LAYOUT_TOP_DOWN()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_TOP_DOWN Sample](http://www.plantuml.com/plantuml/png/xLXhRziw4ltkNy7hV6W3E8sJFfhDEaRzK1vOnmaiPRDtsy9Wf74iN9aKIBgkTzl_laD9PcGpMa7sRJvT1aWKSURCcI5r-FWa5HLgFejghqYFHrn8VDWhRRNQRm5CGWR46JZNpj0Rdz_WhzxDu6P4ziwJLaCaLosZa3rMnFIStkKmHNIl_ksGe-DQJVuHifWAEYDeHEUHyk2xwaJX8vi1KyJ7No3oPWj1u_imK5Dot6pcti_ezskGaZw26_u7oD7xPjvBWAyeUuo0_BT6iBc82bmjOpZdJAKUnqcFdDA0Bp0vCg6HXDhFF4n72Bx889AoahqFIKlUQ2ZxRJx0psSvjLeFVCu2AfRjzehV1ei2paqhmWQFTqbBtdQv240KlTSZ2YIWSWg1flcA3EYIprMr8OuuCXvqVh-vyyOTT-p-m_5wbxcK7wZ_nwFGoMOy7CVfzdivYobbmKA4IW4ZIip1dY0wko6T0Qdt-2pqYKkP9DTklPRE5JBXNFzfJT2E-3hCcO2WVKy5mtgUjWvrHvlq15050PeB4eJIdqiPSjOW322GH77o0EGRZS90MzL-0nOyfMZoNUNgtToE-pVtG_IB4r-k59yXhXvZXDsq7pZdtdXqTN7faGWcIhk8y76gSXvO-6uwAqAe-l5cZilNCCOCg6mG64Vq0QBzt8TGFplBtjR9sWoaacH-vO3wGS_8vu79vxJtQt44p6m44TKfosaOLqmKNSShJaUD5UZn6ZrJqhDwVP-iZFCTne-SQlAcB9N2AF2dRATuNzZXOKlYTtow8PJjpndyrzQXxcyV7jRNQe3S9eBF6cZ6SsETqRQx6gH-SD2kxvTYcCHiCDl6eAxLhOkV_EkLW_Qs2Tfzcc7hu40pB8UoUPOO6V0rz27W5_Z0nJR5nAoBi7OlwlCrDJ6sB2vYba7kNkHDulrjYgk5rQfmV_VI5cFp1IiWMXow7C9cM9h6HldkjYdVtQsLuDtknIj2Zeie5jCl1R2vtLKgss2Rikabsafli7lXYh5XeWg85eSkW2XXEAXKlj4svTER6pl7qUxr-p_WA5w55IpEenp39bcUoTCEcbn254Fb0nWw6tL8OFb-fhNauFCq309WN_i7ISUQprs9pzqpFgCIdz4pFeCIdq7canmNVHx3AUaG6IOxHCadQa45FYobWjaRDBaLuOoA9O48zC5FdX9lQXcIa16fiRI7EuzZBXGYvfnkWSSOWB9WqrTcU-jeINpE63v1G1GdgYJC5LF00hIbyo04vcCUpZSGomSUB1jwepyboOY7FesIk8opWwStSKAeWP0o359YVAwIPpvP3nx0DuXuh3D1I8fbsVRmVkkCt9lXk7knEhatJzuTV-oQVkTVdZCQTWPZo_33YVunXkxlhkTSv_gFZZwSTFisa6NujwHLlIieE1xhpuUpTji-l9kJhdrVaPYM6dGtJgGR5R5FpisFRxiVpWjFyl0ToJ4QZL-Ginc5Kl8d7VrJI3wT_Y_2sKoO8gflUn_FUytoEhyWPtksbzTvztkK-ollSZnmBfnXlpRLkY5DYhK87e45wTr1xSSPMMluluT6v4VjHsjZPhGp2vBEqiJ4P5TakofvtccZ4crjcAdeEgWnB08rJfXGafPzwVAAE9dGLzN3X725sv0qmxMRYZ8m_H20zCNpg5_O5xQoA8YmoNViV5SLEEUKnuQsaNTBe2ISYUScereX2_Cvs-GDs6x4hGWstsqhNqv-vygNXDlXsj1Gh7XxI3wdViMNVDll0NkSAOhKX2IBK4r3HjJBxGfz4xnW7-XjxFAssUJz7Pty226Hi36Ymf-62id8nie1MQIu-9JUbXxAD5KY5PrCjjyizd3HwrmDdL5kz_RkxKc___vFshsPEhx88ctIATzR_BKyLr-UqScgS8PhnldNBE962spzDATkMw2gtgkJ_7pDYrWL7aRGToUq8VuskTrbtoHKNVcDQqNnDraKoVuivam_vsNVE9KBVcxTU5s-SC0-YQEv9F5souGXMx1CkBQiwnWvPTz5lAzlRuOeYpdnFddVxPut_oJnDjdj9jvxpQGLABR9eL2nF-9vgd_oonJxByL6ApCEbbKs1NwLhcVmlrhNJHv5kfvrlxok5vF3bfqtQJ0BaK2ze_-6KWcgkC0RyCrDkt-4HYwTQILB--hxwPURMxaMy32cSOoMz_10Ed4SXNwogwpZgzvUWtJSspT3nqCN0UJupH6v_cTFztMYY2yacKiafGLGqwPeCfj7AjGXFPHR1OAeS0OHnf98yMT6yhLAEn4dCyFEsWYYLN9FjEuaI1tlqlDkNRJIHgRt2UO2bCH_GV_Hryzvbq_0Wlai-Xy0 "LAYOUT_TOP_DOWN Sample")

Using `LAYOUT_LEFT_RIGHT()`

```csharp
@startuml LAYOUT_LEFT_RIGHT Sample
https://raw.githubusercontent.com/DKStudio/C4-PlantUML/master/C4_Container.puml

LAYOUT_LEFT_RIGHT()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_LEFT_RIGHT Sample](http://www.plantuml.com/plantuml/png/xLfjRziu4lwkNy5rFgG1dCP9NvhD9SRwHMc2Svp0KYwtrnO6ROrZOMLI8Ecwlcl_-mrbcP7D28BaDfzM1c9Pd7dccI7ry0NvGoegr7mMEVkamoCk9Dxi5LwEyri0av01SNlkZTltXvUt-ATpsxiTaBtBv78GoLFBA6IF9J5zjtFLNo5wr_znoV69uyY_GXPJGMS4ZUWyKZvyKwqeV6GpO8gCyG-8hDb2qFWX3DIKd3GQcUSp-kq6fAIFu8N_1NByhf7r4Z1Mb3r6GFxd4BmyH0MkbZ5SSgPM7YT9YvpIW2ymEJAXaGJdHnQc9GHVf119MSdU--HAdcWe-sasm8zdEPsVZ_YS1LGicyqrloqMEPmRLeGj7c-JAtdQvY80aVTSzoYGWCef19hcFkdH9P-hSbqSSMJSQ_rvU-yFMzxG-wVhTwuoAO_e-Az7ePDDURYks-vsCXPJoeA529K2HfIOWpr0T7PzEWDIw_1PE2OUPPBSU3LdDLR8X7FzTJxXUlpeC1S2WkO35GphUNP-f1kQf2E0AWZGN90WbEEvb25dTS800aaK9oCWNsaK1jhA-GrOy9IYoNUTgtzxD-pUFlJHBqvykL8S6OUwZn5ssxxdNlh3mVN7Avz4C57QHOIFKvNnmCAtLwCYXB8lR-guV0L3p83AEe5XH4SG7MHUXDh5HVgqHZP689KazIi6r3TwH3uFJ3wjMh_aHy3C1X1HdRASXd79HD5rkEPqN5-3dcpGCoMzgDKEoDeuss3yo9acRyfIAeo2yPJj5EypEpewb_WUdsq9PVDJ2l_b_4YtDu-EQXirG6uJmMTrDEEPlavfsqrrKZiyRDOE2Z5COZQORMDGD-hMnbV-LUgGUDi4xJRDyFpmK3CiXh9v5XWPy0tqFk0REEAYIZ4nwsAioaLzjgOcHiNY8cOnvAv5tYRUhL9SBQnMXRkxbpOVcozOFj6Sq3P48SFYDBRATr-bVFTtLeBtknSl3pdEevXFtmOev7PVgcozAcNJKxILNc_tmkLZmqJb4yq9NG2Hmx1Ngdo3AkNJYnixny7FgLyEE8fNVWLpyx0nYaaMP_AqWYPN4CLGUWE6paOT4bX-a6ejEVmq3OC0s9VkOTAmuNDVu7F_ZC-Wm6VmZ4-lmAUN-YJRnJ6FuOoqY0oJ5QBa4xMW0c-MKi7iDPhSYN16nP9017hZ9y-8FxKCISY8r5ZQmvl7CHSA4JDETy1Z341PiEqhqxLrj2HZpXZUGK0K9weWp3LJm0AqfVCW13R6FDol89OZ7YphUg4_9KcFXsCQ9N4PPuTFJ-A4K1qXPHYiYF6vIkxvP3Du05yXuh7E124fbgNgvltE7NYt_M7xuthdtZXzU_AXRThTV_lkeD_g3It3zwVwOmozFptVlScq7n-_FsrtRI3ByFVaAdjMaBCzrgyFPysclNatErtxl28nBJHeR-r8jofYxvmR7zwqtr_cxkJX6v9ZD1g-86VJ2uNaJrlwaqj-DVnVXBCPC7bKttG-N7OQnNL-GSxsQ2-ky-xdA0_N_jMmvtvq-rrdgdL3cXIT21w11Qkp0-Vx1TcuyBUFHkIxy_ryQsGqKmko6gM9YSakptPTygpJLYMQsZ1LqKrGOvW7QfmmeIGj-z1bdxYfq9VLmuHmYTEGLOQR9nK5OFec03aMpwD-Pf_PsY8dmZRVeVjDbU1iAuzDtaQkb41XE1FFItgrH1OoSR39ss1LYTiHBBvLArzCVjVA5uQhVcneA9OyFIIVLdxvXtpLru0TpXH5QaAIHQYc8IFgvLQ5OnCyPnteRwtogYpo_e5EumWXaR0nec8y3HMIaVMr0x98SFNTwhJqIAvI9LBHoQJwOh63arxhkkyECgktjszEkzrtFsdrPkhu8fEqIQTuRL5-UlvxUaOdgy8fhkddNpE96osmzTFikcs1AdkkJhBZDIjYPNZOWbwPqBRuM-IgoxwLK7dbDwubnTzaaIVxivWpVP-LVUDKAFZPUUDLySG11oIEvfB4rQO9GpPdcl1iMTSnCig-YtZVtDtsKHOpudtwhjs-RFmayJRPxIRUUutaob5iaqEkOd_0_LJtz9Sfzj-AZLPMFnYhT0ZyAbrFuN-rhfiyB5stUBoyhkUGSwn_672ST0DAWrc8Z6ej_HrA9QZY0e_4jrVnu-CwsVVeB8vW_s3r3cVci0MCXZIE4US1HgGLnr4uJjQNDNpKsQkJbdVtkk_ww2A0dBm-9ZV_wkYsLXJnXIHpYMoq5Ee4jCZDvf4AjOpwABmA157X32AC9P7RZvJTAxLgH9pK31kT0KJhh9vetKkGEjwLxzzvQAMDJEiJp4TG4d-2_j87qLcNFu05yrdqVm00 "LAYOUT_LEFT_RIGHT Sample")

## LAYOUT_WITH_LEGEND()

Colors can help to add additional information or simply to make the diagram more aesthetically pleasing.
It can also help to save some space.

All of that is the reason, C4-PlantUML uses colors and prefer also to enable a layout without `<<stereotypes>>` and with a legend.
This can be enabled with `LAYOUT_WITH_LEGEND()`.

```csharp
@startuml LAYOUT_WITH_LEGEND Sample
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_WITH_LEGEND Sample](https://www.plantuml.com/plantuml/png/0/xLfjS-8u4lwUglm7BPagCZS9aCmRboBKyk9CKaU0mkHoUpDRbC02N6jRFaaU9hix__tKVW5iRB1ZoCrLhLCLm6frFq-tBBLR-faBp8HZ6aWGBewFYgZrxhnlO4iyt7VEq5V2k4ujT56gb2hGEXV2vbVbyamNSsTScb2pFD0dc6cqgnER6EMrxiT7hZvgKCRXsydE2thyD3Fe61lebT9HxfNkS7JJa_zQlKvlWAvHuUJ6lGgUSbKy6RerUuRseTAwxNgwrRj_ArBrnIK8yDzqoyOCcqWZK-mOOaY-YOQXpooJM09Dv3_2me8BXkr7NHDpT5cfh3UO-DizuHpFYAh_Jj35-qgu8oCJWQsPGT0VnqT8NghKJQXuiiaDjOJNwT9hudEiqONaYgROuEJuw7i4BHPuZFa-L3KOeuj0Zni-TFB1lRnRe33XzjBEzmIcjTgOEfQ6sLEzleGQnPE0lx9X_frxURURb6c49JR0I27IItnED1zU4NNm4tL4Xj4pTQo9W0UYq_Ybzp0SDTIH-WzbsBezVRrETumdlyqO4FNnA8hIRBVMHUROqXPC5u9OI327n8my8Dh59a655ZNr2LAnnT6zAeU-DmhHb5Bug4qfZ4omTCs8Ld_4p9BUlAgLeQ6EMenWGJGfpf2cyud3uPa-GnOX6aU2eZ51Nx6XQo0bIH9B2tZ6aXxs-gDsxx4Bd0MrNGrK22g1wn1ejzzEBHtbPZWQt7sw7O8UWqm5A6BwR2wswIdAUBe3I2TP9XN7-ez3NIS4C7mrJwUl97NCpz0h0u-98R7yn8Xmc8MAg-UpS7rTVEC9l2aMK6WKOuvacwia2ZUzMVa9Ops5zIzMZSkduKhUYSnXRuhrp_8kw7bJ_BLM1h5wUh3WpG4nCFpYSztEvLsfQEHJl93St2-NQsIN4Ruk52HfNtBjVj07NVcTKlXsbr519dChe_62r_kBLIvxVezwlVxPqniul5mkn8p-MB2dhwQCcW2ChWq_ZyL6onagd9_N0MyQFyGgy81kCn6uADvKejERShxBIgPsVfwMJ9B-J8nYxILQx18v4OqfonoYr17QPY9RgB96wjdaQjaYjZU6jIoHQsSE6Qnb6UBMpXsmh0RfmZeugNWR--6LQFKXCws7VWPI3xaPPJDd7vYEVI0-YHOxcGb1LfU1KYStewm6PPvvS5BnDlR3Az7g83CjD_dEm6kGcrHcY_0sS7XU2LRsn6treebkYM4Jbk-zHQeABK6GmC8FTFvvhciQiNvjdyFz5EH1rSDMLGzPL0ssgXfaKTNPggeJgwg8_lQSArGLwYi3jTSTDJ-j5PmgrNUN7vk5zShKluRAeDleZEB4FrJXRrrS_KKTAlTXgOkB3zLcErPfdFZVtUkvHQ_OEWmCH6fvLPXmiSMhMSJKtuwFTZGt8tMFg3-bn7gLflBnRVF3pRPY4VacaLdO6Bq8sgIuHc1N6_2t3JP_ueAO1qOR6ISHa6zR7szQbLI-VH6qISCxdM-3wkQFxDeLnX_VitieVJxU3Mz77UMJqcr30KzEpGJn9KUewCtazEmLz8wF_hn6eKl-7aenzATigaMdYRelWxodtXTAUZgNqe7RmzqYNgcxebvWeefZHCEALzqaDOzWt6gl60Gs2_AjytsNn6PrCbGMzEv2ZMyvGMAEKXSZOsr0WOpm2OktzSNwOla2wSnkCJnIledK13UNWknCOmncOfi1GomArHq_gIalfuyiJ6DjP6Avs-mMmy-BQGwcUujfBjhjyIRfvPRSleAwOMIDwAQnVKQrFOwFQpp5VOHLMYJR0hkJRwQuxcrNIO6DEPlfd8nsRp0bxWKLLcfIlSNwJq8UYvwA-BVN_EzLBPd0DEwwoY3yMlFkRRNTVh_Nrvg9p9wmRX6sjh-SDlCAxoudYcnaO9liOhQaTsQD_n_8_yeSSsQEijkcrptTon7mCXbcAp0NinVjrxrYbyyCEw4eFAopB0ExqErQvDEZZ2mSgG1lXnotK0SkZLkuNjYZYV1shA-7TkdULk4bqrnBub9BR1LUjoQ68sUku4GSmukITohEuOG1O_c0RZyWLpOnp7lorcXfgsGxfW7afIrgkcVEn9oWAJKCxuoKN2C9md9-33NhZBldPwHjPD09DemdKB946MF2NNCdr2PNg86uxZu_oq2LeBNFT5Dw1X5_jhcIZZLjQi5tj91STSkrlfgtv0qEAjtkgcFRb0a0lQx1b-NeT4q5frEnm8m44sMWw3Mo3OVBUPdQXaSx8idzmqB64y2mv3Sv4AGZF5m1MXVF7OH4aytOqNHYJIHnDL26sMIkoq4iYO4HZNmb1eNLe9Jp56EhTz_lTM4n3cK-rVVDvarbpvcFppPt_d1ISQ_4d27AA2Pd-5XjLDlLhTdEZuhshmpdXJ8SLouQdK3E7nqlbGdvvWwS2Qs6VBPrUpkw0sP2AG1lXtpeJ2YdH_y7cL0gb-PuvuwVWewF_5elramTzgiRyAbpmR2WRe8JhI5CBivGKSMcN7UBhrUdmOEaV4768spRKjCZ6QE6RHioom7u1SYSJivGG-sNkifGTf7BwsNf0jt_imLj3KXaE2Ggp3ry31w15TXq3A738ZzSmAbeXeHk4aXsEA3x7W0y5LwprEGB5bnwSERHvxQ2zi1bR_bvEnpsrOAtZxz2ljBqYSXrNom8VC1MSwZFyT7FCZeoPVel "LAYOUT_WITH_LEGEND() Sample")

## LAYOUT_AS_SKETCH()

C4-PlantUML can be especially helpful during up-front design sessions.
One thing which is often ignored is the fact, that these software architecture sketches are just sketches.

Without any proof

* if they are technically possible
* if they can fullfil all requirements
* if they keep what they promise

More often these sketches are used by many people as facts and are manifested into their documentations.
With `LAYOUT_AS_SKETCH()` you can make a difference.

```csharp
@startuml LAYOUT_AS_SKETCH Sample
!includeurl https://raw.githubusercontent.com/RicardoNiepel/C4-PlantUML/master/C4_Container.puml

LAYOUT_AS_SKETCH()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_AS_SKETCH Sample](https://www.plantuml.com/plantuml/png/0/xLfjS-8u4lwUglm7BPagCZS9aCmRboBKyk9CKaU0mkHoUpDRbC02N6jRFaaU9hix__tKVW5iRB1ZoCrLhLCLm6frFq-tBBLR-faBp8HZ6aWGBewFYgZrxhnlO4iyt7VEq5V2k4ujT56gb2hGEXV2vbVbyamNSsTScb2pFD0dc6cqgnER6EMrxiT7hZvgKCRXsydE2thyD3Fe61lebT9HxfNkS7JJa_zQlKvlWAvHuUJ6lGgUSbKy6RerUuRseTAwxNgwrRj_ArBrnIK8yDzqoyOCcqWZK-mOOaY-YOQXpooJM09Dv3_2me8BXkr7NHDpT5cfh3UO-DizuHpFYAh_Jj35-qgu8oCJWQsPGT0VnqT8NghKJQXuiiaDjOJNwT9hudEiqONaYgROuEJuw7i4BHPuZFa-L3KOeuj0Zni-TFB1lRnRe33XzjBEzmIcjTgOEfQ6sLEzleGQnPE0lx9X_frxURURb6c49JR0I27IItnED1zU4NNm4tL4Xj4pTQo9W0UYq_Ybzp0SDTIH-WzbsBezVRrETumdlyqO4FNnA8hIRBVMHUROqXPC5u9OI327n8my8Dh59a655ZNr2LAnnT6zAeU-DmhHb5Bug4qfZ4omTCs8Ld_4p9BUlAgLeQ6EMenWGJGfpf2cyud3uPa-GnOX6aU2eZ51Nx6XQo0bIH9B2tZ6aXxs-gDsxx4Bd0MrNGrK22g1wn1ejzzEBHtbPZWQt7sw7O8UWqm5A6BwR2wswIdAUBe3I2TP9XN7-ez3NIS4C7mrJwUl97NCpz0h0u-98R7yn8Xmc8MAg-UpS7rTVEC9l2aMK6WKOuvacwia2ZUzMVa9Ops5zIzMZSkduKhUYSnXRuhrp_8kw7bJ_BLM1h5wUh3WpG4nCFpYSztEvLsfQEHJl93St2-NQsIN4Ruk52HfNtBjVj07NVcTKlXsbr519dChe_62r_kBLIvxVezwlVxPqniul5mkn8p-MB2dhwQCcW2ChWq_ZyL6onagd9_N0MyQFyGgy81kCn6uADvKejERShxBIgPsVfwMJ9B-J8nYxILQx18v4OqfonoYr17QPY9RgB96wjdaQjaYjZU6jIoHQsSE6Qnb6UBMpXsmh0RfmZeugNWR--6LQFKXCws7VWPI3xaPPJDd7vYEVI0-YHOxcGb1LfU1KYStewm6PPvvS5BnDlR3Az7g83CjD_dEm6kGcrHcY_0sS7XU2LRsn6treebkYM4Jbk-zHQeABK6GmC8FTFvvhciQiNvjdyFz5EH1rSDMLGzPL0ssgXfaKTNPggeJgwg8_lQSArGLwYi3jTSTDJ-j5PmgrNUN7vk5zShKluRAeDleZEB4FrJXRrrS_KKTAlTXgOkB3zLcErPfdFZVtUkvHQ_OEWmCH6fvLPXmiSMhMSJKtuwFTZGt8tMFg3-bn7gLflBnRVF3pRPY4VacaLdO6Bq8sgIuHc1N6_2t3JP_ueAO1qOR6ISHa6zR7szQbLI-VH6qISCxdM-3wkQFxDeLnX_VitieVJxU3Mz77UMJqcr30KzEpGJn9KUewCtazEmLz8wF_hn6eKl-7aenzATigaMdYRelWxodtXTAUZgNqe7RmzqYNgcxebvWeefZHCEALzqaDOzWt6gl60Gs2_AjytsNn6PrCbGMzEv2ZMyvGMAEKXSZOsr0WOpm2OktzSNwOla2wSnkCJnIledK13UNWknCOmncOfi1GomArHq_gIalfuyiJ6DjP6Avs-mMmy-BQGwcUujfBjhjyIRfvPRSleAwOMIDwAQnVKQrFOwFQpp5VOHLMYJR0hkJRwQuxcrNIO6DEPlfd8nsRp0bxWKLLcfIlSNwJq8UYvwA-BVN_EzLBPd0DEwwoY3yMlFkRRNTVh_Nrvg9p9wmRX6sjh-SDlCAxoudYcnaO9liOhQaTsQD_n_8_yeSSsQEijkcrptTon7mCXbcAp0NinVjrxrYbyyCEw4eFAopB0ExqErQvDEZZ2mSgG1lXnotK0SkZLkuNjYZYV1shA-7TkdULk4bqrnBub9BR1LUjoQ68sUku4GSmukITohEuOG1O_c0RZyWLpOnp7lorcXfgsGxfW7afIrgkcVEn9oWAJKCxuoKN2C9md9-33NhZBldPwHjPD09DemdKB946MF2NNCdr2PNg86uxZu_oq2LeBNFT5Dw1X5_jhcIZZLjQi5tj91STSkrlfgtv0qEAjtkgcFRb0a0lQx1b-NeT4q5frEnm8m44sMWw3Mo3OVBUPdQXaSx8idzmqB64y2mv3Sv4AGZF5m1MXVF7OH4aytOqNHYJIHnDL26sMIkoq4iYO4HZNmb1eNLe9Jp56EhTz_lTM4n3cK-rVVDvarbpvcFppPt_d1ISQ_4d27AA2Pd-5XjLDlLhTdEZuhshmpdXJ8SLouQdK3E7nqlbGdvvWwS2Qs6VBPrUpkw0sP2AG1lXtpeJ2YdH_y7cL0gb-PuvuuxcNnyv5TwiMRgi5lTW4-T2uO5TTERQ0LXSd66YYesvQfRVBqw2nwav0io7c7RbfeUoHWrRDkGEGw0Bq3UT7A66cg_r5M6iejSN2zB5-Z-doreQq0Qmo5DOUxHO_07hB-cOmWTblZX0iv4CoHqaq2gmm7Tzm3WgV2QfIPViE3IWnEFFhSLj0SkUylFs-6mhnQyNVmLyfMcJqIk-c91u0CscaDzVfQHaUdIVm40 "LAYOUT_AS_SKETCH() Sample")
