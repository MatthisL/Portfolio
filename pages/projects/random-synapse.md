---
layout: page
title: Cassandra's Fate
permalink: /random-synapse/
weight: 10
---

<img src="{{ '/assets/img/cf/Logotitre-CF.png' | relative_url }}">


# Table of contents

- [Table of contents](#table-of-contents)
    - [Introduction](#introduction)
    - [Why did I join the project?](#why-did-i-join-the-project)
    - [The Team](#the-team)
    - [My Missions](#my-missions)
        - [User Interface](#1-user-interface)
            - [UI System](#11-ui-system)
            - [Link Front and Back](#12-link-front-and-back)
        - [Gameplay Core](#2-gameplay-core)
        - [Art integration](#3-art-integration)



## Introduction
---

Cassandra's Fate is a CRPG cooperative video game project started in 2021 by a young studio, Random Synapse Studio, founded by a group of freshly graduated friends with their love for cooperative RPGs.
{: .text-justify}

All the team, espacially the funders, was deeply involved in this project. We didn't count our time passed on the features, learning day after day, week after week. 
{: .text-justify}

We were all juniors, reunited around an objective, ambitious, certainly, and driven by our passion for making and playing video games.
{: .text-justify}


We were looking for financial solutions to continue the development of Cassandra's Fate. Unfortunately, after a little more than a year, without successfully finding resources to continue, 
Cassandra's Fate had to be put aside and most of the team had to move on. This is, sadly, the true and realistic life of 99.9% of this kind of projects.
{: .text-justify}

*You maybe have noticed that I've used the pronon "we" instead of "they", and this is natural to me as we all were so involved that this was OUR project, even as a freelance.*


## Why did I join the project?
---


In Septembre 2021, I was finishing more than one year on Unity projects as a freelance, during my 4th and last year of my studies. I absolutely wanted to work with Unreal more seriously.
{: .text-justify}

I heard a ton of good things on this engine and I was convinced that I should learn and cut my teeth with it for the future. In addition, I was really attracted, naturally, by Unreal Engine since a while!
{: .text-justify}

That's why we found each other with Thibaud Vegreville <i>(project leader of Cassandra's Fate back then and funder of Random Synapse Studio)</i> and the rest of the team.
{: .text-justify}


I needed a project to build my knowledge, experiment, learn, and I was thirsty about it (and I still really am!). Furthermore, I love cooperative and RPG, this was the perfect project for me!
I found a relentless and determined team, loving to learn as much as I do. I'm proud to say we grew up in the game making together.
{: .text-justify}

<br/>
**[Back to top 🔼](#table-of-contents)**


## The Team
---

| Name                  | Role                              |
| ----------------------|-----------------------------------|
| Thibaud VEGREVILLE    | Lead Programmer / Game designer   |
| Damien SIEST          | Executive / HR                    |
| Laurent DI SARIO      | Scenarist / Game Designer         |
| Robin ABOU            | Scrum Master / Community Manager  |
| Théo HAGRY            | Programmer                        |
| Adrian GRATTEPANCHE   | Graphic Designer / Artist         |
| Fabrice ROS PATURAUX  | Art Director                      |
| Matthis LE TEXIER     | Programmer                        |

<br/>
**[Back to top 🔼](#table-of-contents)**



## My Missions
---

During my time on the project, we were really focused on core gameplay mechanics such as the battle system, in turn by turn, 
leaving the lore and scenaristic systems behind for the moment (but sadly we never had the time to work on this part seriously).
Thus, I have worked a lot on a thing I truely love in RPG : battle of statistics! Equipment, abilities, statistics,.. So much fun!
{: .text-justify}

I even found myself programming bash scripts to translate excel files into proper CSV format to import in our data system in Unreal Engine and fluidify Game Design process.
{: .text-justify}

<blockquote>
See the helper command I could retrieve from our old discord server (I have sadly no more access to the project's cloud drive as I'm writing this in 2025 😔)...


<details>
    <summary>Expand Me</summary>

    {% highlight plaintext %}
        PS D:\Unreal\Cassandras-Fate\Script> Get-Help .\ExcelConverter.ps1 -full

        NAME
            D:\Unreal\Cassandras-Fate\Script\ExcelConverter.ps1

        SYNOPSIS
            Convert a table located in a worksheet of an excel file into an Unreal formatted CSV.


        SYNTAX
            D:\Unreal\Cassandras-Fate\Script\ExcelConverter.ps1 [[-XLPath] <String>] [[-SheetName] <String>] [[-StartCell] <Int32[]>] [[-OutputFolder] <String>] [[-OutputName] <String>] [-UseRowName]
            [<CommonParameters>]


        DESCRIPTION
            Unreal datatable systeme uses CSV format to import/export. This script can convert part of the GameDesigner's data located in excel files into a format
            that can be imported as DataTable in Unreal, aka CSV.
        PARAMETERS
            -XLPath <String>
                Specifies the path to the excel file.

                Required?                    false
                Position?                    1
                Default value
                Accept pipeline input?       false
                Accept wildcard characters?  false

            -SheetName <String>
                Specifies the name of the worksheet where belong the data table to convert to CSV.

                Required?                    false
                Position?                    2
                Default value
                Accept pipeline input?       false
                Accept wildcard characters?  false

            -StartCell <Int32[]>
                Specifies the left up corner coordinates of the data table to look up for in the worksheet, aka the starting cell. (1,1) by default (A1).

                Required?                    false
                Position?                    3
                Default value                @(1,1)
                Accept pipeline input?       false
                Accept wildcard characters?  false

            -OutputFolder <String>
                Specifies where the output CSV will be saved.

                Required?                    false
                Position?                    4
                Default value                UnrealCSV
                Accept pipeline input?       false
                Accept wildcard characters?  false

            -OutputName <String>
                Specifies the name of the output CSV.

                Required?                    false
                Position?                    5
                Default value
                Accept pipeline input?       false
                Accept wildcard characters?  false
            -UseRowName [<SwitchParameter>]
                The first column of the Unreal DataTable is the "RowName".
                If this parameter is specified, the first column of the table in the excel will be used as the RowName column.

                Required?                    false
                Position?                    named
                Default value                False
                Accept pipeline input?       false
                Accept wildcard characters?  false

            <CommonParameters>
                This cmdlet supports the common parameters: Verbose, Debug,
                ErrorAction, ErrorVariable, WarningAction, WarningVariable,
                OutBuffer, PipelineVariable, and OutVariable. For more information, see
                about_CommonParameters (https:/go.microsoft.com/fwlink/?LinkID=113216).
        INPUTS
            None. You cannot pipe objects to ExcelConverter.ps1.


        OUTPUTS
            If successfull, creates or override (with confirmation) a CSV file into $(Get-Location)/UnrealCSV by default. This can be overrided with the OutputFolder parameter.
            The file name would be as follow if not specified : ExcelFilename_WorksheetName.csv. This can be overrided with the OutputName parameter.


            -------------------------- EXAMPLE 1 --------------------------

            PS>.\ExcelConverter.ps1 -XLPath ./MyExcel.xlsx -SheetName Sheet1






            -------------------------- EXAMPLE 2 --------------------------

            PS>.\ExcelConverter.ps1 -XLPath ./MyExcel.xlsx -SheetName Sheet1 -OutputFolder ./MyOutputFolder -OutputName MyOutput






            -------------------------- EXAMPLE 3 --------------------------

            PS>.\ExcelConverter.ps1 -XLPath ./MyExcel.xlsx -SheetName Sheet1 -UseRowName
    {% endhighlight %}              
</details>
</blockquote>

<br/>
**[Back to top 🔼](#table-of-contents)**

<br/>

### 1. User Interface

I remember that I spent a looooot of time on the User Interface. Nobody, in the programmer team (we were 3..) wanted to do it. And I never did it so I was pretty excited about it (cool, a new thing to learn !). 
Back in time, I did a bit of web development because I was satisfying to code and see the results in realtime with HTML/CSS.
{: .text-justify}

In the same way, that's the reason why I appreciate to build and develop tools for my team: my work is directly in the hands of the user and help him/her!
{: .text-justify}

In the early stage, I had to do mockups and placeholder interfaces for the game. It's really straightforward and classic widgets for an RPG as you can see.
{: .text-justify}

The true challenges was to apprehend the UMG (Unreal Motion Graphics) tool to build-up the interfaces and connect them to the ton of datas we had in the gameplay.
{: .text-justify}

Knowing that we were using the Gameplay Ability System framework.


<br/>

**[Back to top 🔼](#table-of-contents)**

<br/>

<!-- <div class="alert alert-warning" role="alert"> -->

#### 1.1. UI System

At first, every menus was fullscreen, like the character details:

{% capture carousel_images %}
{{ '/assets/img/cf/cf-early-character-details-1.png' | relative_url }}
{{ '/assets/img/cf/cf-early-character-details-2.png' | relative_url }}
{{ '/assets/img/cf/cf-early-character-details-3.png' | relative_url }}
{% endcapture %}
{% include elements/carousel.html id="carousel-character-details" %}

*Notice the humble design change depending on the class you play, amazing 👀*
{: .text-center}
<br/>

Further back in time, we changed our plan and wanted to have a window/panel system for the interfaces, you know that one, notably from famous MMORPG!
{: .text-justify}

Thus, I developed a complete system from scratch with UMG tools I had at my disposal, mainly using drag and drop system:
{: .text-justify}


<img src="{{ '/assets/img/cf/cf-early-windows.png' | relative_url }}">

The objective was to have windows you can drag and drop anywhere, with focus system and draw priority system, where windows draw on top of each other. 
When clicking on a window you can see behind, you regain the focus on it and it brings it back on top of others.
{: .text-justify}

For the widget architecture, I created a parent for all panel widget containing:
- the header (which is a button to be able to drag&drop the panel) with the close button
- a Named Slot Widget which will be overriden in the childs to create new panels

This way, to create a new panel, it's as simple as creating a child blueprint of `W_BasePanel`, and fill the NamedSlot with new content. Panel header's title will be filled with the `Name` variable and every panel has now the same behavior with different content, and voilà!
{: .text-justify}


<br/>

**[Back to top 🔼](#table-of-contents)**

<br/>

#### 1.2. Link Front and Back

Cassandra's fate was using a lot of datas for character statistics, attributes, abilities,... We were coupling **Data Driven** logic, with data assets, and **Gameplay Ability System** framework to consume those datas.

My additional work on the UI was to 
- safely retrieve the necessary datas for the widgets, 
- refresh them correctly, 
- and in some cases, handle the replication.

Here are some examples of mock-ups for different panels in the game:

{% capture carousel_images  %}
{{ '/assets/img/cf/cf-ability-tooltip-1.png' | relative_url }}
{{ '/assets/img/cf/cf-ability-tooltip-2.png' | relative_url }}
{{ '/assets/img/cf/cf-ability-tooltip-3.png' | relative_url }}
{% endcapture %}
{% include elements/carousel.html id="carousel-ability" %}


<div class="alert alert-warning" role="alert">
    <h5>Abilities and their properties: </h5>
    <li>dynamic tooltip description displaying calculated damages depending on a lot of other data such as character's statistics</li>
    <li>Icon, of course</li>
    <li>Name, of course</li>
    <li>Mana cost</li>
    <li>Cooldown</li>
    <li>Scaling attributes</li>
</div>

---

{% include elements/video.html id="5PjpzF6e76w" %}
<div class="alert alert-warning" role="alert">
Abilities equip quickbar drag & drop <i>(sorry for the music, but still important to work with good music in the ears!)</i>
</div>

---

{% capture carousel_images  %}
{{ '/assets/img/cf/cf-ability-tooltip-1.png' | relative_url }}
{{ '/assets/img/cf/cf-ability-tooltip-2.png' | relative_url }}
{{ '/assets/img/cf/cf-ability-tooltip-3.png' | relative_url }}
{% endcapture %}
{% include elements/carousel.html id="carousel-character-creation" %}
<div class="alert alert-warning" role="alert">
Start character creation process
</div>

---

{% include elements/video.html id="WQEOjMJu-t0" %}
<div class="alert alert-warning" role="alert">
Battle Encounter System (very early and bad quality 😅)
</div>

---

<img src="{{ '/assets/img/cf/cf-item-tooltip.png' | relative_url }}">
<div class="alert alert-warning" role="alert">
Items tooltips with statistics comparaison with the one equipped by the character.
</div>

<br/>
**[Back to top 🔼](#table-of-contents)**

<br/>

### 2. Gameplay Core

<br/>
```
Coming...
```
<br/>

### 3. Art integration


During the entire time in the project, I had the mission to work closely with the art team. 

I was in charge to help import and integrate art asset into Unreal:
- Animations
- Meshes
- 3D Model for environment
- Weapons
- Help with VFX