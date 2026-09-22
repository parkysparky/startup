# CS 260 Notes

- [My startup](https://startup.cs260.click)
- [My simon](https://simon.cs260.click)

## Helpful links

- [Course instruction](https://github.com/webprogramming260)
- [MasteryLS](https://masteryls.com/)
- [Canvas](https://byu.instructure.com)
- [MDN](https://developer.mozilla.org)

## Web Server Setup  
We are using a preconfigured server for this class.  
AMI ID: `ami-094c4a0be0b642a24` located within the region `US East (N. Virginia) - us-east-1`  
  
### AWS

Oodles of services. Important to set budgets. Any more than 1 elastic IP costs money. I set one so I can use the same IP and associate it with a domain name.  

Access the server from the production directory with the following command:  
`ssh -i keys/production.pem ubuntu@wechoose.click`  

### DNS  
Domains have levels like in the reference image below  
![subdomain.secondary.top](./images/domainNameParts.jpg)


## HTML

**anchor** tag example
```html
<a href="https://github.com/parkysparky/"> author</a>
```

**img** tag example (consider verifying open source image here)
```html
<img src="https://imgs.search.brave.com/5K7j_XVJQwU6JRe8g-TdYe4lyGfwyhp1wuWUotCRsw8/rs:fit:500:0:1:0/g:ce/aHR0cHM6Ly9pbWFn/ZS5zaHV0dGVyc3Rv/Y2suY29tL2ltYWdl/LXBob3RvL2NvbXBv/c2l0aW9uLXZhcmll/dHktZnJ1aXRzLXdp/Y2tlci1iYXNrZXQt/MjYwbnctNjQ1NzQ2/NTMuanBn" alt="Fruit Basket" width="200"> </img>
```


## CSS 
Prof. Christiansen said if we do all 24 levels of [Flexbox Froggy](https://flexboxfroggy.com/) he would give a little extra credit.  
### Responsive Design
Viewport
Display Types  
![Types of Responsive Design](./images/readme/responsiveDesignTypes.png)


The most important is **flex** probably followed by **grid**  

**Flex** Justify is parallel to direction. align-content is perpendicular to direction. default is horizontal.   

**Frameworks** - premade CSS package that offers numerous classes and functions. Bootstrap is the most popular followed by Tailwind   F 



## React

Interesting things I have learned about React



For a required commit I must input the following text: I love web programming
