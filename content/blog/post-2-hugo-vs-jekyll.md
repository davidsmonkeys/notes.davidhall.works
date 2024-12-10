---
title: First steps into blogging
type: blog
sidebar:
  open: true
---

## Preamble

For reference it's Nov 2024 and the contract market is not as bouyant as it has been and as a result I'm really having to sell myself which I'm not great at. I'm not one to promise things that I'll have a go at and for want of a better idiom "wing it". As a contractor I feel that I have already learnt and applied the skills that I'm selling into buisness. 

I accept that having the exact knowledge for a tailored output id difficult if not impossibe and at best you can have previously applied it somewhere else however this is unlilekly and to use a nother idiom the "chicken and the egg" issue. Also if its over 5 years since applying something it's likely changed and my expierence is no longer the expience for working with a given technology. 

I think in short I'm trying to get round to saying that I'm wring a blog to communicate stuff I've done and showcase a level of adaptability that should allow me to appraoch unique problems with a expectation from expience and with the right aboutn of pragmaism produce an outcome that desirable. 

In order to do that I need to communicate what I'm capable of through documented means that is publically availbale. I could do a podcast if verbal was my prefence but then how would I copy and paste? 

## Looking for a platform

I found a great webiste by jamstack that allowed me to review a few of the static site generators that are available it's a big field and Imight change my mind however I tried Jeckyll written on Ruby and Hugo written on Go.




## Decition that I've made

I've decided to go with Hugo. The primary reason for this is that I'm running on WSL and using dev containers and there is some issue with file system change notifications from the windows files systen to the linux one that means that I could not get the Jekyll to live reload. (I'm not saying that it doesn't and there are likely workarounds)

Hugo on the other hand let me run the website locally under a polling mechansim. Hence the better solution for producing website using markdown where I can see the changes that I make in the browser before deploying. 

Secondly I note that Hugo doesn't come with a defult theme but I have chosen to go with [Hextra](https://imfing.github.io/hextra). as this appears to support most of the things that I'm looking for such as associated comments, code snippets and collapsable areas. 

With the exption of getting started I also wanted a way to update the blog through PR so that I can review the content. I also wanted to utilise git hub pages for hosting of which the Hextra tempalte supports through git hub actions. (I note that Jekyll will do this too.) Information [here](https://imfing.github.io/hextra/docs/guide/deploy-site/)

I want to be working with Markdown and I want the articles to be self contained through markdown so that if I decide that I want to move to another framework/site generator I can do that easily.

I didn't want to use a full CMS such as WIX or wordpress as I don't need the interaction with the end users as per the audience of me and if I do want to do that I can replicate my article on something such as dev.to or medium. 

## Hosting on github pages

Hosting on github pages is reasonable stright forward however I had some issues with images that we're not being deployed. 

{{% details title="Trouble with Images" closed="true" %}}

On deploying the site to github pages the iamges are not loading. On inveitgation using browser tools I see that I'm getting "206 partial content". 

In the iamge I was using a direct reference "mountains.png" as the image lives in the same folder as the file. When checking what is being loaded generated as the output I see 

```
<img src="./mountains.png" alt="mountains" loading="lazy" />
```

This results in the URL from the published site looking for 

```
"https://notes.davidhall.works/mountains.png" 

```
which is the right location accorsing to what is exported to the /public directory. 

Now I want to be able to snip screenshots and publish them which I managed to get working with the below image declared as 
```
![homepage screenshot](post2-screenshot-homepage.png)
```
However for some reason I needed to put that image in a sub folder inside the blog directory. 

![file structure](file-structure.png)

resulting in

![homepage screenshot](post2-screenshot-homepage.png)

** The thing to note here is that the assets need renaming and moving to a folder with the same name as the blog in the source. This results in the generation putting the images under a folder for the blog. (Using VS code and snipping tool for screenshots)

{{% /details %}} 




## Building my blogging envionment



## References 

https://jamstack.org/generators/
List of static site generators. Thier languages and github details. 

https://jekyllrb.com/
The main website for Jekyll

https://gohugo.io/
The primary website for Hugo

https://imfing.github.io/hextra
The inforamtion about the Hextra theme and how to use it. 