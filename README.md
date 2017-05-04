# How to create and deliver an Open Badge ? The definitive quick and easy Open Badge tutorial.

Mozilla has a great documentation regarding Open Badges ecosystem and use, but also quite complex in regards to an Open Badge mvp. Below are working examples tied to this repo along with the expected steps tutorial.

Although if you prefer, you can follow [the official step by step tutorial](https://github.com/mozilla/openbadges-backpack/wiki/New-Issuers:-Give-Yourself-a-Badge), as well as reading [the official specification](https://github.com/mozilla/openbadges-specification).

## Requirements 
- What you need before anything :

* [ ] one image representing your badge
> You can use this tool to build one : [Chicago Badge tudio](http://toolness.github.io/chicago-badge-studio/studio.html)

- What you will build with this tutorial :
* [ ] one "issuer" json file
* [ ] one "badge class" json file
* [ ] one "badge assertion" json file
* [ ] one github repo used for hosting the badge files
* [ ] one "baked badge" image file

## Step1 : Defining the issuer
Basically you, or your organisation : the one that will deliver the badge.

```
{
    "name": "insert your name",
    "url": "insert your personal or company url"
}
```

Documentation : 

## Step2 : Defining the badge class
Basically, the definition for the badge that you want to award, including criterias, image and issuer.

```
{
    "name": "insert the badge class name",
    "description": "insert the description for your badge class",
    "image": "insert the url to the badge image file",
    "criteria": "insert the url to your badge criterias HTML page",
    "issuer": "insert the url to your badge issuer json file "
}
```

Documentation :

## Step3 : Defining the badge assertion
This is the "real" badge that you will "physically" deliver. It should be unique for each awardee you grant it to. Exists in at least 2 forms : /*to complete*/

_Note_ : Although it is specified the "image" option is optionnal, I couldn't validate any assertion without it. 

```
{
  "uid": "insert a unique identifier",
  "recipient": {
    "identity": "insert the email of the awardee",
    "type": "email",
    "hashed": false
  },
  "issuedOn":  insert a timestamp,
  "badge": "insert the url to your badge class json file",
  "verify": {
    "type": "hosted",
    "url": "insert the url to the awardee badge award json file (this actual json file)"
  },
  "image":"insert the url to the badge image"
}
```

## Step 4 : Uploading and validating
In order to validate the badge assertion schema, you need your ressources to be online. Easyer way to do so, is to actually :

1. fork this repo on your account
2. activate [Github pages](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/#enabling-github-pages-to-publish-your-site-from-master-or-gh-pages) for the fork
3. modify the paths in the 3 .json badge files with the Github pages url
4. add them to the /json folder
5. Push :)

Once your done, you can submit your assertion structure here for validation :

> [Open Badges Validator](http://validator.openbadges.org/)

## Step 5 : Bake the badge you're about to deliver
This step will merge the assertion with your badge image, so you have a portable badge to deliver.

> [Open Badges Bakery](http://bakery.openbadges.org/)

## Step 6 : Add to backpack !
This is the last step, create an account and upload your baked badge to see it displayed.

> [Open Badges Backpack](https://backpack.openbadges.org/)

Hope this tutorial helped, any contribution is more than welcome ! 

Also, if you want to add this tutorial badge to your backpack, open an issue with your mail or a pr, i'll gladly award you one !