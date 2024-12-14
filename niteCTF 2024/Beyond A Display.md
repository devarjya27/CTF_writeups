# Challenge Description
I took a metro from this location and I saw a shopping complex in the vicinity. I remembered that I saw a multidimensional billboard from a company over there. The same company held a concert on 26th October 2024, and a group performed there. However, I have forgotten what the information really was. Can you help me? Flag format: nite{Billboard_Company,Group_Name,Venue_Of_The_Performance}

Category: `OSINT`

[Attachment](https://play.nitectf2024.live/files/c1df0824dcc5a1c5bfd07ba062385545/beyond_a_plane.png?token=eyJ1c2VyX2lkIjo3OSwidGVhbV9pZCI6NDAsImZpbGVfaWQiOjExOH0.Z13KZw.xB5xMWQ3-DTNrb6brLtqEg_FXjk)

# My Solve
Reverse image searching the provided image I found out that the image is from `Gurgaon`. Now looking up `multidimensional billboards from gurgaon` i came across this article [Hyundai 4D Billboard](https://www.afaqs.com/news/marketing-initiatives/hyundai-earns-spot-in-asia-book-of-records-with-indias-first-4d-billboard-for-the-new-creta).

Now I searched for `Hyundai Concerts` and found out that Hyundai organizes something called `Hyundai Spotlight` where they hold concerts exclusively for Hyundai owners. Now looking at their [site](https://hyundaispotlight.in/) they did organize a show on `26th October 2024` headlined by `Shankar Ehsaan Loy` and the venue- [KTPO](https://www.instagram.com/hyundaiindia/p/DAI_PdOp9SK/?hl=en)

Therefore the flag (following the format given) would be `nite{Hyundai,Shankar_Ehsaan_Loy,KTPO}`.
