# Lab Report 3: Researching Commands

- Name: Eric Yan
- PID: A17341154

- In this lab report, I will show 4 interesting options to use the command `grep`

## The `grep -r` option

- `grep -r PATTERN DIRECTORY` reads all files under the given directory recursively and return all the lines that contain the given patterns as strings.
- Example1

    ```text
    03:15 PM ericyan ~/CSE/CSE15L/lab4 (main)$ grep -r "New York City" written_2/
    written_2/non-fiction/OUP/Rybczynski/ch1.txt:Not only are function and form separate, over their long lives buildings can successfully accommodate a variety of uses. For example, some of the most famous museums (the Louvre, the Hermitage, the Belvedere) started life as royal palaces; the Uffizi in Florence is so named because it originally housed offices; and the Prado in Madrid was designed to be a museum of science, not art. The acclaimed Musée d’Orsay in Paris is housed in a railroad station. Two of my favorite small museums, the Frick Collection in New York City and the Phillips Collection in Washington, D.C., were built as residences. As historic preservation and adaptive reuse demonstrate, you can shop in a renovated warehouse, do office work in a converted loft, or live in a barn. Assuming, of course, that the warehouse, the loft, and the barn were well built. The material fabric of old buildings—the heavy beams, rough brick walls, and solid woodwork—is one of their chief pleasures. That is why we feel cheated by hollow walls, flimsy doors, and shaky balustrades. Buildings should last and feel as though they will.
    written_2/non-fiction/OUP/Rybczynski/ch1.txt:Yet delight is not uniform. The Main Concourse of Grand Central Terminal in New York City, for example, offers different pleasures than Thirtieth Street Station. The monumental spaces are comparable in size and function. They are both well built. Similar spaces, similar materials, yet the experience of the two concourses is different. Both buildings are inspired by the Classical architecture of the past, but Grand Central, which opened in 1913, is a modified version of Beaux-Arts Classicism, whereas the Philadelphia station, despite the Corinthian columns, is simplified, abstracted, and stylized, what historians called “stripped Classicism.” As a result, Grand Central is dramatic, visually rich in its details, almost Wagnerian; Thirtieth Street is equally dramatic but in a way that is coolly geometrical and sleekly urbane—not Wagner, Cole Porter. Style is evident in the smallest details. It ensures a continuity between the great vaulted sky of Grand Central and the ticket counters, or between the Thirtieth Street chandeliers and the announcement boards at each track stair. It is the visual language of a building. Architectural style is the manner in which the architect communicates a particular kind of visual delight, in large ways and small.
    written_2/non-fiction/OUP/Rybczynski/ch2.txt:The Kennedy Center was criticized from the start, but the dazzling décor of Radio City Music Hall, which opened in 1932—in the midst of the Depression—guaranteed its immediate success. Radio City became the most famous theater in the country, the Rockettes the most famous chorus line, “live from Radio City” the most famous dateline. In the late 1950s, when I visited New York City as a boy with my parents, Radio City was still one of the obligatory tourist sites. What I don’t remember is ever learning about Radio City as an architecture student. According to the reductive standards of my International Style teachers, its opulent materials, its glowing colors, and its very theatricality disqualified Radio City as architecture (never mind that it was a technologically sophisticated “machine for entertainment”). It was dismissed as kitsch. By 1978, Radio City had lost its glamour, and the owners of Rockefeller Center decided to demolish the aging hall. Thanks to preservationists’ efforts, the hall was saved from demolition and granted landmark status. Now, 20 years later, freshened by a masterful restoration, it is once again acclaimed as a masterpiece.
    written_2/non-fiction/OUP/Rybczynski/ch2.txt:In North America, Gothic was, if anything, even more popular. Canadians chose a British architect and the Gothic style for their Houses of Parliament, which stand on a dramatic bluff overlooking the Ottawa River. Anglophile Americans built Collegiate Gothic campuses, Gothic parish churches, and a Gothic National Cathedral in Washington, D.C. Ralph Adams Cram, who was devoted to High Gothic, built the nave and west front of New York City’s Cathedral Church of St. John the Divine, the largest Gothic structure in the world. Cram’s partner Bertram Goodhue used a looser Gothic style in the military academy at West Point, as did Cass Gilbert in the Woolworth Building—the so-called Cathedral of Commerce. By then the cultural attributes of Gothic had worn thin. Hood’s Chicago Tribune Building, completed in 1924, was one of the last prominent buildings designed in the Gothic style.
    written_2/non-fiction/OUP/Rybczynski/ch2.txt:Architecture changes at a bewildering pace. Consider only the last 50 years of museum design. The National Gallery of Art (1937-41) in Washington, D.C. and the Museum of Modern Art (1937-39) in New York City are almost exact contemporaries. In the MoMA design, Philip L. Goodwin and Edward Durrell Stone ignored the Classical tradition represented by John Russell Pope’s masterpiece. MoMA’s entrance was not up a broad flight of exterior steps but through a revolving door. Goodwin and Stone replaced the monumental rotunda by a nondescript lobby, the lofty galleries by low-ceilinged loft spaces, and limestone and marble by stucco and plasterboard. MoMA was to be the last word in avant-garde International Style, but it was scarcely finished when it was challenged by Frank Lloyd Wright’s Guggenheim Museum (1943-58), which rejected the banality of the white box by squeezing the entire museum into a dramatic sculptural spiral. Nothing could be further from the International Style than the mollusk-like exterior (especially if it had been tinted rose-red, as Wright initially wanted). In the Yale Center for British Art (1969-77), Louis I. Kahn likewise incorporated central skylit spaces, but he disavowed Wright’s loud anti-urban exterior by hugging the sidewalk and clothing his building in drab stainless steel panels. Kahn preached taming technology by consigning it to so-called servant spaces; in the Centre Georges Pompidou (1971-77), Piano and Rogers stood Kahn’s dictum on its head and gave the servants the run of the house. In the Neue Staatsgalerie (1977-83), James Stirling cheekily lifted architectural elements from both the Pompidou and the Guggenheim and combined them with a variety of historical styles. I. M. Pei’s impeccably crafted East Building of the National Gallery of Art (1976-78) in Washington, D.C., had not one exposed bolt, not one allusion to the past. Pei rejected both Stirling’s eclecticism and Piano and Rogers’ technological posturing. Instead he relied on abstract geometry for architectural effect. Frank O. Gehry’s California Aerospace Museum (1982-84) in Los Angeles is no less abstract and geometrical, but his forms bump and grind into each other almost as if by accident. “I really enjoy the awkwardness with which [the forms] touch,” Gehry observed, “as it reminds me of the cities we live in and the kind of awkwardnesses of city buildings sitting next to each other.”6 The cost of the East Building was $94.4 million; the Aerospace Museum was built on a tight budget of only $3.4 million. Lacking money for refinement, Gehry turned awkwardness into a virtue, and in the process disowned Pei’s fastidious brand of modernism. He was carefree where Pei was careful, spontaneous where Pei was studied, brash where Pei was genteel. The Aerospace Museum was clearly not a cheaper version of the East Building, it was something different.
    written_2/non-fiction/OUP/Abernathy/ch1.txt:In the late 1940s, Bond Stores, the largest men’s clothing chain at the time, created a sensation in New York City by offering a wide selection of suits with two pairs of pants instead of one, reintroducing a level of product choice not seen since before the war.1 When the line of hopeful buyers at its Times Square store stretched around the block, Bond had to impose a limit of two suits per customer. During World War II, the apparel and textile industries had been converted to supply field jackets, overcoats, and uniforms to the U.S. and Allied Forces. But in the years immediately following the war, returning soldiers, the end of rationing, and pent-up customer demand meant apparel was in short supply.
    written_2/non-fiction/OUP/Abernathy/ch1.txt:When people consider the U.S. apparel industry, they often think of New York City’s Seventh Avenue, which is driven by new design, constantly changing seasonal offerings, and a willingness by consumers to pay a premium for the cutting edge of fashion. New York City and Los Angeles continue to have a competitive advantage in this area because a large number of designers and manufacturers are located in these cities and can respond quickly to changing demands, as well as shape them. This infrastructure allows for “quick response” on the fashion end of the women’s and, to a more limited extent, men’s markets. Once established, a variety of proponents believe, the experience at the fashion end can be diffused downward to less fashion-oriented products. As a result, some of the fashion-oriented products that had been sourced offshore can then return to the United States.
    written_2/non-fiction/OUP/Abernathy/ch15.txt:The El Monte plant in southern California, with immigrants working behind barbed wire, caught the nation’s attention in 1996. Federal investigators reported in 1997 that two-thirds of the establishments in New York City’s garment industry violated overtime or minimum wage laws.24 The U.S. Labor Department reports that independent surveys, as well as federal and state compliance data, show minimum wage and overtime violations of the FLSA occurring in 40 to 60 percent of investigated establishments. The policy question is what, if anything, can be done to control or eliminate sweatshops and noncompliance with statutory standards in the United States? And what can be done to ameliorate sweatshop conditions in developing countries that produce and export half of the apparel purchased in this country?
    written_2/travel_guides/berlitz2/China-WhereToGo.txt:Probably the smallest of all the Suzhou gardens, situated right in the center of town, is the Garden of the Master of the Nets (Wangshiyuan), covering half a hectare (barely more than an acre). The garden’s founder, a retired politician, claimed he had given up public life to become a fisherman. Whatever his interests, he could hardly fail to be inspired by the view from his simple study. This gem is considered the masterpiece of Chinese classical garden design and served as the inspiration for the Astor Chinese Garden Court in New York City’s Metropolitan Museum of Art. 
    written_2/travel_guides/berlitz1/WhatToJapan.txt:        prices than those in New York City, still the world’s reigning discount
    ```

  - In this example, I search the pattern *New York City* in the directory **written_2**. The output displays all the lines that contain *New York City* and name of the file that contain the line at the beginning. You can see that these files come from different subdirectories of **written_2** instead of one directory. That shows how `grep -r` search a directory recursively.
- Example2

    ```text
    03:34 PM ericyan ~/CSE/CSE15L/lab4/written_2/non-fiction/OUP/Abernathy (main)$ grep -r "unless"
    ch9.txt:These issues aside, there is one other major task a sewing operator performs. She must make the pieces of the pattern fit together at the end of the sewing process. This is certainly not possible if there has been a big mistake in cutting, but it is never easy, even without serious cutting errors. If two plies of flat cloth of identical length are placed on top of each other and sewn together, then the ends of the two pieces will not line up without the intervention of a sewing operator. The two ends of a thirty-inch leg seam on a pair of jeans, for instance, might be a quarter of an inch out of alignment unless the operator takes control. During sewing, the feed-dog on the machine—a part that comes up through two slots in the stitch plate and engages the bottom ply of cloth—will pull the bottom ply under the presser foot and against the pull of the thread. The top ply of cloth is carried along by the bottom ply; hence, one ply is stretched more than the other.
    ch9.txt:The investment per worker in a sewing room is quite modest. A simple new commercial sewing machine may cost $2,000 to $3,000, but a rebuilt machine can run as low as five hundred dollars and still provide a good dozen years of production. The average annual capital investment in sewing machines and attachments per operator in our survey was $720 (in 1992 dollars). Some of the machines in an American men’s dress-shirt plant like the one previously described will cost $20,000 or more, but such automated sewing systems are rare. As we have already noted, the general requirement for return on investment forces expensive capital equipment to be operated under more than single-shift conditions, unless it is essential to produce a given item. The automated sewing systems that create the closely spaced regular stitch patterns used as decorative top stitching on men’s dress shirts, collars, cuffs, and pockets are examples of expensive machines operated for a single shift.
    ch15.txt:Our less pessimistic view of the future of these industries should not be misinterpreted. The textile sector appears more promising because it has become more directly connected to retailers and industrial users. Yet survival in both sectors belongs only to the fittest adopters of the new order of retailing and the channel. Employment levels are not projected to turn around. Instead, employment will gradually decline in both industries, while output and productivity increase—the best that any industrial sector can expect over time in the modern economy. The new order in apparel places more of a premium on scale and size, along with investments in the requisite technologies. The traditional contractor shop and small enterprise will have a smaller and even less secure role unless linked to sophisticated intermediary agents in the channel.
    ch14.txt:Meanwhile, modular production allows apparel suppliers to reduce the time required for a given product to move through the assembly process. For instance, by substantially reducing work-in-process buffers in assembly, throughput time on the modular lines of business units in the HCTAR sample dropped to just two days, compared with nine days for standard assembly methods. But the benefits of throughput-time reduction cannot be fully realized unless firms are rewarded for their ability to replenish rapidly. Rapid replenishment, in turn, requires the availability of detailed demand data and its frequent and accurate transmission. Finally, suppliers must be capable of using this data to allocate production capacity between short-cycle (modular) and standard (progressive bundle system) production lines. In this way, modular assembly systems only yield real advantages in the presence of the other three practices.
    ch14.txt:Rather than continuing to increase inventory, Compaq announced that it would only assemble its new line of personal computers as its retail customers ordered them. And, instead of providing an open-ended guarantee on prices to its distributors, the company would guarantee the price for only two weeks after purchase by the distributor, refusing to take back computers unless they malfunctioned. By changing its method of distributing products, Compaq hopes to reduce the level of dealer inventory across product lines to two weeks’ worth and in the process save $1 billion or more a year. These cost savings will be used to reduce prices and compete more aggressively with Dell and Gateway 2000 that do not work through distributors.27 Therefore, Compaq’s competitive strategy arises from its efforts to advance information-integration forward in the channels in which it operates.28 Note also that if Compaq seeks to take full advantage of these changes in distribution, it must also adjust its production strategies to account for differences in demand variability across the computer maker’s product lines.
    ```

  - In this example, I search for the pattern *unless* but don't give a directory. If you don't give a subdirectory to `grep -r`, it will search the working directory recursively by default. Thus, you can see that the ouput displays all the lines that contain *unless in the files at the subdirectories of `Abernathy` (the current working directory).
- `grep -r` can be very useful when you want to recursively find all the files and their lines that contain a pattern under a directory.
- Reference: `man grep`

## The `grep -v` option

- `grep -v PATTERN FILE` outputs all the lines that don't contain the given pattern in the given file.

- Example 1

    ```text
    03:54 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ cat HandRIbiza.txt 

  
  
    
      
        Recommended Hotels
        The establishments listed below offer a cross-section of
        local restaurants, and should convince you that not everything on the
        island comes with chips (french fries).
        The star rating in brackets after each entry refers to the
        offfical government rating system.
        As a basic guide, the symbols we use indicate what you can
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        ✪less than 5,000 ptas.
        ✪✪5,000–8,000 ptas.
        ✪✪✪more than 8,000 ptas.
      
    
  
    03:55 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -v "expect" HandRIbiza.txt

    
    
        
        
            Recommended Hotels
            The establishments listed below offer a cross-section of
            local restaurants, and should convince you that not everything on the
            island comes with chips (french fries).
            The star rating in brackets after each entry refers to the
            offfical government rating system.
            As a basic guide, the symbols we use indicate what you can
            tip. Drinks will add considerably to the final bill.
            ✪less than 5,000 ptas.
            ✪✪5,000–8,000 ptas.
            ✪✪✪more than 8,000 ptas.
    ```

  - In this example, we can see that `grep -v` elimimantes the line that contains *expect* compared to the original content of the file
- Example 2

    ```text
    03:56 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -v "8,000" HandRIbiza.txt 

  
  
    
      
        Recommended Hotels
        The establishments listed below offer a cross-section of
        local restaurants, and should convince you that not everything on the
        island comes with chips (french fries).
        The star rating in brackets after each entry refers to the
        offfical government rating system.
        As a basic guide, the symbols we use indicate what you can
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        ✪less than 5,000 ptas.
    ```

  - In the same file, when I give the pattern *8000* to `grep -v`, it outputs all the lines that don't contain *8000* compared to the original file.
- When you want to delete all the lines that contain a pattern in a file, it's useful to use `grep -v` so that you don't have to delete them manually.
- [Reference](https://www.youtube.com/watch?v=Tc_jntovCM0)

## The `grep -n` option

- `grep -n PATTERN FILE` displays the line that match the pattern and their line numbers

- Example 1

    ```text
    04:33 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ cat HandRIstanbul.txt 

  
  
    
      
        Recommended Hotels
        Finding accommodation in Istanbul is rarely a problem, as
        the city has recently seen a boom in the hotel business. However, if
        you want a room in a particular hotel, it is best to book, especially
        during July and August. The main hotel areas are Laleli, Aksaray, and
        Sultanahmet in the Old City, and around Taksim Square in Beyo‘lu.
        Intense competition among the middle-range hotels means that you can
        often bargain for a lower rate, especially if you plan to stay for more
        than two nights.
        As a basic guide we have used the symbols below to indicate
        prices for a double room with bath, including breakfast:
        ❁❁❁❁❁over £130 ($200)
        ❁❁❁❁£80–130 ($120-200)
        ❁❁❁£50–80 ($75-120)
        ❁❁£30–50 ($45-75)
        ❁below £30 ($45
    ```

    ```text
    04:33 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -n "often" HandRIstanbul.txt 
    13:        often bargain for a lower rate, especially if you plan to stay for more
    ```

  - In this example, `grep -n` not only outputs the line that contain *often* but also its line number 13.
- Example 2

    ```text
    04:38 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -n "in" HandRIstanbul.txt
    7:        Finding accommodation in Istanbul is rarely a problem, as
    8:        the city has recently seen a boom in the hotel business. However, if
    9:        you want a room in a particular hotel, it is best to book, especially
    10:        during July and August. The main hotel areas are Laleli, Aksaray, and
    11:        Sultanahmet in the Old City, and around Taksim Square in Beyo‘lu.
    13:        often bargain for a lower rate, especially if you plan to stay for more
    15:        As a basic guide we have used the symbols below to indicate
    16:        prices for a double room with bath, including breakfast:
    ```

  - In the same file, `grep -n` displays multiple lines that contain *in* and the line number of each line.
- `grep -n` makes it easier for you to go back to the original file to fined the matched lines. Then, you may want to edit that line or see the text before and after that line.
- Reference: `man grep`

## The `grep -w` option

- `grep -w PATTERN FILE` only returns the lines that match the **whole word** of pattern in the given file

- Example1

    ```text
    04:45 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ cat HandRLisbon.txt 

  
  
    
      
        Recommended Hotels
        Hotel prices in Lisbon have risen in recent years to match
        most western European destinations, even surpassing popular cities like
        Barcelona at the top levels. Many hotels offer special packages (such
        as summer or weekend reductions).
        Central Lisbon covers the area from the waterfront, Bairro
        Alto, Lapa, and Avenida da Liberdade. North Lisbon refers to the area
        around and beyond Praça Marquês de Pombal. Pousadas, found beyond
        Lisbon, are government-owned hotels and inns; the ones listed occupy
        historic buildings, and their restaurants are usually among the town’s
        best.
        The price indication given is for a double room, with
        breakfast, including service and taxes (currently 5 percent of room
        price) in high season (generally April–October).
        $$$$$over 40,000 esc
        $$$$30,000–40,000 esc
        $$$20,000–30,000 esc
        $$12,000–20,000 esc
        $ below 12,000 esc
    ```

    ```text
    04:46 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep "in" HandRLisbon.txt 
        Hotel prices in Lisbon have risen in recent years to match
        most western European destinations, even surpassing popular cities like
        Lisbon, are government-owned hotels and inns; the ones listed occupy
        historic buildings, and their restaurants are usually among the town’s
        The price indication given is for a double room, with
        breakfast, including service and taxes (currently 5 percent of room
        price) in high season (generally April–October).
    04:48 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -w "in" HandRLisbon.txt 
        Hotel prices in Lisbon have risen in recent years to match
        price) in high season (generally April–October).
    ```

  - In this example, I first search the word *in* in the file "HandRLisbon.txt" as normal. However, the output is a bit out of expectation because `grep` also returns lines that contain words like *destinations* that contain *in* within them. If you only want to search for the whole word *in*, `grep -w` can be helpful. In the following command, I add the `-w` option. This option only returns lines that contain the whole word of `in`. In other words, `in` must be preceded with a non-word constituent character (like space) and followed by a non-word constituent character.
- Example 2

    ```text
    04:48 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep "is" HandRLisbon.txt
        Hotel prices in Lisbon have risen in recent years to match
        Central Lisbon covers the area from the waterfront, Bairro
        Alto, Lapa, and Avenida da Liberdade. North Lisbon refers to the area
        Lisbon, are government-owned hotels and inns; the ones listed occupy
        historic buildings, and their restaurants are usually among the town’s
        The price indication given is for a double room, with
    04:59 PM ericyan ~/CSE/CSE15L/lab4/written_2/travel_guides/berlitz1 (main)$ grep -w "is" HandRLisbon.txt
        The price indication given is for a double room, with
    ```

  - In this example, I search for the word *is* in the same file. Similarly, if we use `grep` without any options, lines that contain words like *Lisbon*, *risen* are also returned. On the other hand, when I use `grep -w`, only the lines that contain the whole word *is* is returned.
- `grep -w` is very helpful when you only want to find lines that match whole words in any texts.
- Reference: `man grep`