---
permalink: /running
---

A few years ago, I realized I needed a hobby that involved more than Netflix and my couch. I passed by KC's [Trolley Track trail](https://www.traillink.com/trail/harry-wiggins-trolley-track-trail/) one day and I thought it would be nice to give it a little walk. So I grabbed a hoodie and some old Asics I found in the closet and started walking. I was getting bored after about a block so I started to up the pace a bit until I was going at a pace which could be described as "slightly faster than a walk". I was tired after about a quarter of a mile.

I kept at it and _eventually_ made it a whole mile without stopping. And then a mile and a half. And then a whole 5k. Needless to say, I was hooked.

A few years later (and many pairs of [Brooks Adrenaline running shoes](https://www.brooksrunning.com/en_us/brooks-adrenaline-gts-running-shoes/) later), I'd logged over 4,500 miles on Strava--mostly on the Trolley Trail but I've found a bunch of other fun routes in KC.

Here are my PRs:

<table>
    <thead>
        <tr>
            <th style="text-align: right">Distance</th>
            <th>Race Name</th>
            <th>Location</th>
            <th style="text-align: right">Finish Time</th>
            <th style="text-align: right">Average Pace</th>
            <th style="text-align: center">Strava Link</th>
            <th style="text-align: center">Event Results Link</th>
        </tr>
    </thead>
    <tbody>
        {% for race in site.data.running-prs %}
        <tr>
            <td style="text-align: right">{{race.distance}}</td>
            <td>{{race.event.name}}</td>
            <td>{{race.event.location}}</td>
            <td style="text-align: right"><span class="pr-time">{{race.finish-time}}</span></td>
            <td style="text-align: right"><span class="pr-time">{{race.average-pace}}</span><span class="pr-min-per-mi">min/mi</span></td>
            <td style="text-align: center"><a href ="{{race.strava-link}}"><i class="fab fa-strava fa-2x"></i></a></td>
            <td style="text-align: center"><a href ="{{race.event.results-link}}"><i class="fas fa-running fa-2x"></i></a></td>
        </tr>
        {% endfor %}
    </tbody>
</table>
