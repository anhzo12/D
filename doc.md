## uBlock and AdGuard Rules

### uBlock script for Opera

```ini
!facebook #######
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##:xpath("//div[@aria-posinset and .//*[name()='use']/parent::*[name()='svg' and (number(substring-before(substring-after(@style, 'margin-right:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) > 56.885 and (number(substring-before(substring-after(@style, 'margin-right:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) < 56.895]]"):upward(6)
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[aria-posinset]:has(svg[style$="width: 56.8906px;"]:has(use)):upward(6)
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##:xpath("//div[@aria-posinset and .//*[name()='use']/parent::*[name()='svg' and (number(substring-before(substring-after(@style, 'margin-left:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) > 61.63 and (number(substring-before(substring-after(@style, 'margin-left:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) < 61.65]]"):upward(6)
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##:xpath("//div[@aria-posinset and .//*[name()='use']/parent::*[name()='svg' and (number(substring-before(substring-after(@style, 'margin-right:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) > 61.63 and (number(substring-before(substring-after(@style, 'margin-right:'), 'px')) + number(substring-before(substring-after(@style, 'width:'), 'px'))) < 61.65]]"):upward(6)

facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[aria-posinset]:has-text(Reels và video ngắn):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[aria-posinset]:has-text(Những người bạn có thể biết):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[aria-posinset]:has-text(Reels):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##[aria-label="Mở thước phim trong Công cụ xem của Reels"]:remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[style^="border-radius: max(0px, min(8px,"] > div > div > div > div:has-text(Những người bạn có thể biết):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##[aria-posinset]:has(h4 [role=button]:has-text(/^Theo dõi$/)):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##[aria-posinset]:has(h4 [role=button]:has-text(/^Tham gia$/)):remove()
facebook.com,facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion##div[aria-posinset]:has-text(Sponsored):remove()
www.facebook.com##[aria-label="Được tài trọ"]:upward(19)

www.facebook.com##[aria-label="Những người bạn có thể biết"]:upward(19)
www.facebook.com##[aria-label="Lời mời kết bạn"]:upward(19)


!youtube ######
! Title: Hide YouTube Shorts
! Description: Hide all traces of YouTube shorts videos on YouTube
! Version: 1.10.0
! Last modified: 2024-08-31 19:24
! Expires: 2 weeks (update frequency)
! Homepage: https://github.com/gijsdev/ublock-hide-yt-shorts
! License: https://github.com/gijsdev/ublock-hide-yt-shorts/blob/master/LICENSE.md

! Remove empty spaces in grid
www.youtube.com##ytd-rich-grid-row,#contents.ytd-rich-grid-row:style(display: contents !important)

! Hide all videos containing the phrase "#shorts"
www.youtube.com##ytd-grid-video-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))
www.youtube.com##ytd-rich-item-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))

! Hide all videos with the shorts indicator on the thumbnail
www.youtube.com##ytd-grid-video-renderer:has([overlay-style="SHORTS"])
www.youtube.com##ytd-rich-item-renderer:has([overlay-style="SHORTS"])
www.youtube.com##ytd-video-renderer:has([overlay-style="SHORTS"])
www.youtube.com##ytd-item-section-renderer.ytd-section-list-renderer[page-subtype="subscriptions"]:has(ytd-video-renderer:has([overlay-style="SHORTS"]))

! Hide shorts button in sidebar
www.youtube.com##ytd-guide-entry-renderer:has(yt-formatted-string:has-text(/^Shorts$/i))
! Tablet resolution
www.youtube.com##ytd-mini-guide-entry-renderer:has(.title:has-text(/^Shorts$/i))

! Hide shorts sections except on history page
www.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytd-rich-section-renderer:has(#title:has-text(/(^| )Shorts( |$)/i))
www.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytd-reel-shelf-renderer:has(.ytd-reel-shelf-renderer:has-text(/(^| )Shorts( |$)/i))

! Hide shorts tab on channel pages`
! Old style
www.youtube.com##tp-yt-paper-tab:has(.tp-yt-paper-tab:has-text(Shorts))
! New style (2023-10)
www.youtube.com##yt-tab-shape:has-text(/^Shorts$/)

! Hide short remixes in video descriptions and in suggestions beside the comments
www.youtube.com##ytd-reel-shelf-renderer:has(#title:has-text(/(^| )Shorts.?Remix.*$/i))

! Hide shorts category on homepage and search pages
www.youtube.com##yt-chip-cloud-chip-renderer:has(yt-formatted-string:has-text(/^Shorts$/i))

!!! MOBILE !!!

! Hide all videos in home feed containing the phrase "#shorts"
www.youtube.com##ytm-rich-item-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))

! Hide all videos in subscription feed containing the phrase "#shorts"
m.youtube.com##ytm-item-section-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))

! Hide shorts button in the bottom navigation bar
m.youtube.com##ytm-pivot-bar-item-renderer:has(.pivot-shorts)

! Hide all videos with the shorts indicator on the thumbnail
m.youtube.com##ytm-video-with-context-renderer:has([data-style="SHORTS"])

! Hide shorts sections except on history page
m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-rich-section-renderer:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts( |$)/i))
m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-reel-shelf-renderer.item:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts( |$)/i))

! Hide shorts tab on channel pages
! Old style
m.youtube.com##.single-column-browse-results-tabs>a:has-text(Shorts)
! New style (2023-10)
m.youtube.com##yt-tab-shape:has-text(/^Shorts$/)

! Hide short remixes in video descriptions and in suggestions below the player
m.youtube.com##ytm-reel-shelf-renderer:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts.?Remix.*$/i))

! Hide shorts category on homepage
m.youtube.com##ytm-chip-cloud-chip-renderer:has(.yt-core-attributed-string:has-text(/^Shorts$/i))

! Jun 8, 2025 https://www.facebook.com
www.facebook.com##.x8du52y.x1164lod.xmzvs34.xwib8y2.xf159sx.x1y1aw1k.x1yc453h.x13fj5qh.xat24cr.x1xegmmw.xdj266r.xjb2p0i.x1ypdohk.x1o6z2jb.x1i1ezom.x1otrzb0.xhk9q7s.x1f0uuog.xaqea5y.x12wdn4z.x6umtig.x78zum5.html-div

! Jul 20, 2025 https://www.facebook.com
www.facebook.com###_r_4oj_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d > .xh8yej3.x5yr21d
www.facebook.com###_r_4oj_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d
www.facebook.com###_r_4oj_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div
www.facebook.com###_r_4ih_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d > .xh8yej3.x5yr21d
www.facebook.com###_r_4ih_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d
www.facebook.com###_r_4ih_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo
www.facebook.com###_r_3o8_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d > .xh8yej3.x5yr21d
www.facebook.com###_r_3o8_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo > .xh8yej3.x10l6tqk.x1us6l5c.x5yr21d
www.facebook.com###_r_3o8_ > .x1n2onr6.x1c1uobl.x18d9i69.xyri2b.xexx8yu.x1lziwak.xat24cr.x14z9mp.xdj266r.html-div > .x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo
www.facebook.com##.xh8yej3.x10l6tqk.x1us6l5c.x5yr21d > .xh8yej3.x5yr21d
www.facebook.com##.xh8yej3.x10l6tqk.x1us6l5c.x5yr21d
www.facebook.com##.x3awd8m.x1db0b2.x16zosiy.xh8yej3.x1n2onr6.x10wlt62.x6ikm8r.xl56j7k.x1egiwwb.x1q0g3np.x78zum5.x5omr3n.x1k1lpwg.xjppbhk.xfrllxf.xal61yo

! Sep 14, 2025 https://www.facebook.com
www.facebook.com##.x8du52y.x1164lod.xmzvs34.xwib8y2.xf159sx.x1y1aw1k.x1yc453h.x13fj5qh.xat24cr.x1xegmmw.xdj266r.xjb2p0i.x1ypdohk.x1ihp6rs.xr2y4jy.x1whfx0g.x1i5p2am.x1f0uuog.xaqea5y.x12wdn4z.x6umtig.x78zum5.html-div

! Dec 26, 2025 https://www.rophim.li
||i.finallygotthexds.site/vpromolink/a9/06/a906307f7d0f89413dd8a6002d046635/a906307f7d0f89413dd8a6002d046635.gif$image
www.rophim.li##.is-catfish.is-wide.sspp-area
||i.finallygotthexds.site/vpromolink/6e/0c/6e0c71402195fe2d406d44981b0bac70/6e0c71402195fe2d406d44981b0bac70.gif$image
www.rophim.li##div.is-wide.sspp-area:nth-of-type(3)
www.rophim.li##div.is-3x2.sspp-area:nth-of-type(2)

! Dec 27, 2025 https://www.rophim.li
||i.finallygotthexds.site/vpromolink/e4/b2/e4b2eea27144ea2e98fbae1de6121d3e/e4b2eea27144ea2e98fbae1de6121d3e.gif$image


! fallback theo text
facebook.com##div[aria-posinset]:has-text(Được tài trợ):remove()
facebook.com##div[aria-posinset]:has-text(Gợi ý cho bạn):remove()
facebook.com##div:has-text(Sponsored):upward(10)


```

### AdGuard script for Opera

```ini
facebook.com###mount_0_0_uf > div > div:first-child > div.x9f619.x1n2onr6.x1ja2u2z > div.x9f619.x1n2onr6.x1ja2u2z:nth-child(4) > div.x78zum5.xdt5ytf.x1n2onr6.x1ja2u2z > div.x78zum5.xdt5ytf.x1n2onr6.xat3117.xxzkxad > div.x78zum5.xdt5ytf.x1t2pt76.x1n2onr6.x1ja2u2z.x10cihs4:first-child > div.x9f619.x1ja2u2z.x78zum5.x2lah0s.x1n2onr6.xl56j7k.x1qjc9v5.xozqiw3.x1q0g3np.x1t2pt76.x17upfok:first-child > div.x9f619.x1ja2u2z.x78zum5.x1n2onr6.x1r8uery.x1iyjqo2.xs83m0k.xeuugli.x1qughib.x1cy8zhl.xozqiw3.x1q0g3np.xylbxtu.x1t2pt76.xornbnt > div.x9f619.x1ja2u2z.x78zum5.x1n2onr6.x1iyjqo2.xs83m0k.xeuugli.xl56j7k.x1qjc9v5.xozqiw3.x1q0g3np.x1iplk16.x1mfogq2.xsfy40s.x1wi7962.xpi1e93:nth-child(3) > div.x9f619.x1n2onr6.x1ja2u2z.x78zum5.xdt5ytf.x2lah0s.x193iq5w.xeuugli > div.x9f619.x1n2onr6.x1ja2u2z > div.xw7yly9.xh8yej3 > div.x78zum5.x1q0g3np.xl56j7k:last-child > div.x193iq5w.xvue9z.x17zi3g0.x1ceravr.x1v0nzow > div.x1hc1fzr.x1unhpq9.x6o7n8i:last-child > div > div:last-child > div.x1lliihq:nth-child(44) > div > span > div.x1lliihq > div > div.x1n2onr6.xh8yej3.x1ja2u2z.xod5an3 > div.x1n2onr6.x1ja2u2z > div > div > div.x1a2a7pz > div.x78zum5.xdt5ytf > div.x9f619.x1n2onr6.x1ja2u2z > div.html-div.xdj266r.x14z9mp.xat24cr.x1lziwak.xexx8yu.xyri2b.x18d9i69.x1c1uobl.x78zum5.x1n2onr6.xh8yej3 > div.x1n2onr6.x1ja2u2z.x1jx94hy.xw5cjc7.x1dmpuos.x1vsv7so.xau1kf4.x9f619.xh8yej3.x6ikm8r.x10wlt62.xquyuld > div > div.html-div.xdj266r.x14z9mp.xat24cr.x1lziwak.xexx8yu.xyri2b.x18d9i69.x1c1uobl:nth-child(13)
```

### uBlock script for Edge

```ini
m.youtube.com##ytm-pivot-bar-item-renderer:has(.pivot-shorts)
m.youtube.com##ytm-video-with-context-renderer:has([data-style="SHORTS"])
m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-reel-shelf-renderer.item:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts( |$)/i))
m.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytm-rich-section-renderer:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts( |$)/i))
m.youtube.com##.single-column-browse-results-tabs>a:has-text(Shorts)
m.youtube.com##yt-tab-shape:has-text(/^Shorts$/)
m.youtube.com##ytm-chip-cloud-chip-renderer:has(.yt-core-attributed-string:has-text(/^Shorts$/i))
m.youtube.com##ytm-item-section-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))
m.youtube.com##ytm-reel-shelf-renderer:has(.reel-shelf-title-wrapper .yt-core-attributed-string:has-text(/(^| )Shorts.?Remix.*$/i))

www.youtube.com##ytd-grid-video-renderer:has([overlay-style="SHORTS"])
www.youtube.com##ytd-rich-item-renderer:has([overlay-style="SHORTS"])
www.youtube.com##ytd-video-renderer:has([overlay-style="SHORTS"])
www.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytd-reel-shelf-renderer:has(.ytd-reel-shelf-renderer:has-text(/(^| )Shorts( |$)/i))
www.youtube.com##:matches-path(/^(?!\/feed\/history).*$/)ytd-rich-section-renderer:has(#title:has-text(/(^| )Shorts( |$)/i))
www.youtube.com##tp-yt-paper-tab:has(.tp-yt-paper-tab:has-text(Shorts))
www.youtube.com##yt-chip-cloud-chip-renderer:has(yt-formatted-string:has-text(/^Shorts$/i))
www.youtube.com##yt-tab-shape:has-text(/^Shorts$/)
www.youtube.com##ytd-grid-video-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))
www.youtube.com##ytd-guide-entry-renderer:has(yt-formatted-string:has-text(/^Shorts$/i))
www.youtube.com##ytd-item-section-renderer.ytd-section-list-renderer[page-subtype="subscriptions"]:has(ytd-video-renderer:has([overlay-style="SHORTS"]))
www.youtube.com##ytd-mini-guide-entry-renderer:has(.title:has-text(/^Shorts$/i))
www.youtube.com##ytd-reel-shelf-renderer:has(#title:has-text(/(^| )Shorts.?Remix.*$/i))
www.youtube.com##ytd-rich-grid-row,#contents.ytd-rich-grid-row:style(display: contents !important)
www.youtube.com##ytd-rich-item-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))
www.youtube.com##ytm-rich-item-renderer:has(#video-title:has-text(/(^| )#Shorts?( |$)/i))
```

## Fix conflict RST when dual boot 
Description: After booting the dual boot to the bios, Windows only allow RST/VMD meanwhile Linux Mint only availabel to access when bios setting at AHCI 
> Boot to window -> open CMD run by admin
>> bcdedit /set {current} safeboot minimal
> Restart to bios -> change System Setting in bios 
>> RST/VMD -> Disabled
>> AHCI -> Enabled
>> Save the setting and boot to Window again (Window will update AHCI driver automatic)
> In safemode -> open CMD run by admin
>> bcdedit /deletevalue {current} safeboot


## Tool change partition driver
> Minitool partition wirzad
