# CSZ CMS Stored XSS v1.3.0

## Author: (Sergio)

**Description:** CSZ CMS 1.3.0 is affected by a Stored Cross-Site Scripting (XSS) vulnerability that allows attackers to execute arbitrary code via a crafted payload to the Additional Meta Tag parameter in the Site Settings Menu that will appear both on the main page and on the subpages. 

---

### POC:


When logging into the panel, we will go to the "Site Settings" section off General Menu [http://localhost/admin/carousel]

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/a22eef46-7ec1-4810-b59b-ce5b3807e398)




We edit that Site Settings that we have created and see that we can inject arbitrary Javascript code in the Additional Meta Tag field.


### XSS Payload:

```js
<img src=1 onerror=alert("XSS")
```


In the following image you can see the embedded code that executes the payload in the main web and the subpages:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/caf39bb0-2216-43b6-aa61-2be8b2005a36)

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/40d0bea2-fee0-4c18-b297-e2f2d57ba800)

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/bf2f5520-b0ce-49ec-9a27-56715c0e5c96)

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/2c39cc59-0ea3-4fbb-aee0-392f7252135f)

If we log in with another user, the payload also skips:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Site-Settings/assets/87250597/e93bfae1-797f-4094-afb8-f340917e98e8)


</br>
