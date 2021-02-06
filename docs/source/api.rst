API Reference
*************

VATSEA and VATWA HQ will share the same coding for both systems. Therefore, this documentation will use both domain to be shown as the example.

Change the example domain to **hq.vatwa.net/api/** for VATWA HQ or **hq.vat-sea.com/api/** for VATSEA HQ. Please note that there is a maximum limit 30 requests/hour/IP address for all routes.

Region, division, and subdivision code used below can be found at :doc:`here <hq-member-code>`.

=====
Event
=====

Retrieve all events
""""""""""""""

``http://hq.vat-sea.com/api/events/all``

This endpoint will return all events in HQ.

Response::

    [
	  {
	    "id": 1,
	    "title": "Amman Thursday Night",
	    "description": "Fly into/out of Amman's Queen Alia Intl. Airport [OJAI] every week on Thursday night with full ATC from 1600z to 1900z!",
	    "start": "2020-08-20 16:00:00",
	    "end": "2020-08-20 19:00:00",
	    "banner_link": "https://i.imgur.com/7cr6kTn.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28469-aug-20th-16z-19z-amman-thursday-night/"
	  },
	  {
	    "id": 2,
	    "title": "Surabaya In/Out",
	    "description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
	    "start": "2020-08-20 16:00:00",
	    "end": "2020-08-20 19:00:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	  },
	  {
	    "id": 5,
	    "title": "An event that will end in the future",
	    "description": "<p>An event that will end in the future</p>",
	    "start": "2020-11-28 02:12:00",
	    "end": "2020-12-18 03:30:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	  }
    ]

Retrieve future events
"""""""""""""""""

``http://hq.vat-sea.com/api/events/future``

This endpoint will return all incoming events in HQ.

Response::

    [
	  {
	    "id": 5,
	    "title": "An event that will end in the future",
	    "description": "<p>An event that will end in the future</p>",
	    "start": "2020-11-28 02:12:00",
	    "end": "2020-12-18 03:30:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	  }
    ]

Retrieve past events
"""""""""""""""

``http://hq.vat-sea.com/api/events/past``

This endpoint will return all past events in HQ.

Response::

    [
	  {
	    "id": 1,
	    "title": "Amman Thursday Night",
	    "description": "Fly into/out of Amman's Queen Alia Intl. Airport [OJAI] every week on Thursday night with full ATC from 1600z to 1900z!",
	    "start": "2020-08-20 16:00:00",
	    "end": "2020-08-20 19:00:00",
	    "banner_link": "https://i.imgur.com/7cr6kTn.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28469-aug-20th-16z-19z-amman-thursday-night/"
	  },
	  {
	    "id": 2,
	    "title": "Surabaya In/Out",
	    "description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
	    "start": "2020-08-20 16:00:00",
	    "end": "2020-08-20 19:00:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	  }
    ]

Retrieve specific event
""""""""""""""""""

``http://hq.vat-sea.com/api/event/{id}``

This endpoint will return an event.

Example: ``http://hq.vat-sea.com/api/event/2``

Response::

    {
	  "id": 2,
	  "title": "Surabaya In/Out",
	  "description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
	  "start": "2020-08-20 16:00:00",
	  "end": "2020-08-20 19:00:00",
	  "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	  "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
    }

Retrieve confirmed ATC in an event
"""""""""""""""""""""""""""""

``http://hq.vat-sea.com/api/event/{id}/atc``

This endpoint will return all confirmed ATC for an event.

Example: ``http://hq.vat-sea.com/api/event/1/atc``

Response::

    [
	  {
	    "position": "WAAF_CTR",
	    "controller": "Web One (1000001)"
	  },
	  {
	    "position": "WAMM_TWR",
	    "controller": "Web Two (1000002)"
	  },
	  {
	    "position": "WAMM_APP",
	    "controller": "Web Three (1000003)"
	  }
    ]

Retrieve event by region
"""""""""""""""""""

``http://hq.vat-sea.com/api/events/region/{code}``

This endpoint will return all ATC in a region.

Example: ``http://hq.vat-sea.com/api/event/region/APAC``

Response::

    [
	  {
	    "id": 2,
	    "title": "Surabaya In/Out",
		"description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
		"start": "2020-08-20 16:00:00",
		"end": "2020-08-20 19:00:00",
		"banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
		"event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  },
	  {
	    "id": 5,
	    "title": "An event that will end in the future",
	    "description": "<p>An event that will end in the future</p>",
	    "start": "2020-11-28 02:12:00",
	    "end": "2020-12-18 03:30:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  }
    ]

Retrieve event by division
"""""""""""""""""""""

``http://hq.vat-sea.com/api/events/division/{code}``

This endpoint will return all ATC in a division.

Example: ``http://hq.vat-sea.com/api/event/division/SEA``

Response::

    [
	  {
	    "id": 2,
	    "title": "Surabaya In/Out",
		"description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
		"start": "2020-08-20 16:00:00",
		"end": "2020-08-20 19:00:00",
		"banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
		"event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  },
	  {
	    "id": 5,
	    "title": "An event that will end in the future",
	    "description": "<p>An event that will end in the future</p>",
	    "start": "2020-11-28 02:12:00",
	    "end": "2020-12-18 03:30:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  }
    ]

Retrieve event by vACC
"""""""""""""""""

``http://hq.vat-sea.com/api/events/vacc/{code}``

This endpoint will return all ATC in a vACC.

Example: ``http://hq.vat-sea.com/api/event/vacc/IDN``

Response::

    [
	  {
	    "id": 2,
	    "title": "Surabaya In/Out",
		"description": "Surabaya is one of the largest aviation hubs in Indonesia, it is also the second largest city in Indonesia and boast a huge number of international flight due to its popularity as a tourism and business destination.\n                                In this event, we will attempt to give you the sensation of flying into one of the busiest airspaces in Indonesia.",
		"start": "2020-08-20 16:00:00",
		"end": "2020-08-20 19:00:00",
		"banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
		"event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  },
	  {
	    "id": 5,
	    "title": "An event that will end in the future",
	    "description": "<p>An event that will end in the future</p>",
	    "start": "2020-11-28 02:12:00",
	    "end": "2020-12-18 03:30:00",
	    "banner_link": "https://cdn.discordapp.com/attachments/475903576707694602/747523206486687794/IN-OUT-WARR.png",
	    "event_referrer": "https://forums.vatsim.net/topic/28762-online-day-inout-surabayawarr/"
	    "region": "APAC",
	    "division": "SEA",
	    "vacc": "IDN"
	  }
    ]

===
FSS
===

Retrieve all FSS
"""""""""""

``http://hq.vat-sea.com/api/fss/all``

This endpoint will return all FSS in HQ.

Example: ``http://hq.vat-sea.com/api/fss/all``

Response::

    [
	  {
	    "controller": "Web Five (10000005)",
	    "position": "ASEA_FSS",
	    "rating": "Controller (C1)",
	    "division": "SEA",
	    "region": "APAC"
	  }
    ]

Retrieve FSS by division
"""""""""""""""""""

``http://hq.vat-sea.com/api/fss/division/{code}``

This endpoint will return all FSS in a division.

Example: ``http://hq.vat-sea.com/api/fss/division/SEA``

Response::

    [
	  {
	    "controller": "Web Five (10000005)",
	    "position": "ASEA_FSS",
	    "rating": "Controller (C1)",
	    "division": "SEA",
	    "region": "APAC"
	  }
    ]

=======
General
=======

Retrieve member's info
"""""""""""""""""

``http://hq.vat-sea.com/api/member/{cid}``

This endpoint will return member data. It will also return staff position if member is a staff and mentor information if member is a mentor.

Example: ``http://hq.vat-sea.com/api/member/10000007``

Response::

    {
	  "cid": 10000007,
	  "name": "Seven Web",
	  "atc_rating_id": 9,
	  "atc_rating_name": "Instructor (I1)",
	  "pilot_rating_id": 15,
	  "pilot_rating_name": "P1, P2, P3, P4",
	  "region_code": "EUR",
	  "region_name": "Europe",
	  "division_code": "UK",
	  "division_name": "UK",
	  "vacc_code": null,
	  "vacc_name": null
    }

Retrieve member's approval
"""""""""""""""""""""

``http://hq.vat-sea.com/api/member/{cid}/approval``

This endpoint will return member approval for resident, visiting, and FSS.

Example: ``http://hq.vat-sea.com/api/member/10000004/approval``

Response::

    [
	  {
	    "approved_for": "DEL,GND,TWR,DEP,APP,CTR",
	    "vacc": "IDN"
	  },
	  {
	    "approved_for": "ASEA_FSS",
	    "vacc": null,
	    "is_fss": true,
	    "division": "SEA"
	  }
    ]

Retrieve member's approval for FSS
"""""""""""""""""""""""""""""

``http://hq.vat-sea.com/api/member/{cid}/approval/fss``

This endpoint will return member approval for FSS.

Example: ``http://hq.vat-sea.com/api/member/10000004/approval/fss``

Response::

    {
	   "approved_for": "ASEA_FSS",
	   "division": "SEA"
    }

Retrieve member's approval for resident/visiting
"""""""""""""""""""""""""""""""""""""""""""

``http://hq.vat-sea.com/api/member/{cid}/approval/vacc``

This endpoint will return member approval for resident and visiting.

Example: ``http://hq.vat-sea.com/api/member/10000004/approval/vacc``

Response::

    [
	  {
	    "approved_for": "DEL,GND,TWR,DEP,APP,CTR",
	    "vacc": "IDN"
	  }
    ]

====
News
====

Retrieve a news
""""""""""

``http://hq.vat-sea.com/api/news/{id}``

This endpoint will return a news.

Example: ``http://hq.vat-sea.com/api/news/1``

Response::

    {
	  "subject": "VATSEA Member Protection Policy",
	  "content": "<p>The <strong>VATSEA Member Protection Policy</strong> will be enforced effective immediately. The Division Policy will be updated shortly to include&nbsp;this newly added regulation.</p>\n\n            <blockquote>\n            <p>With immediate effect, ALL VATSIM members and Virtual Area Control Centers (vACC) under the South East Asia Division (VATSEA) are prohibited to post, distribute or demonstrate any forms of political, racial and/or religious material in all official VATSIM channels.</p>\n            \n            <p>This includes social media platforms including but not limited to Facebook pages and groups, Discord and WhatsApp.</p>\n            \n            <p>Members who fail to comply with this regulation will be subjected to disciplinary action.</p>\n            </blockquote>\n            \n            <p>If you have any questions, kindly private message me on discord or drop me an email at <a href='mailto:isaactan.vatsea@gmail.com'>isaactan.vatsea@gmail.com</a></p>\n            \n            <p>Thank you for your attention</p>",
	  "created_by": "Web Four (10000004)"
    }

Retrieve news by region
""""""""""""""""""

``http://hq.vat-sea.com/api/news/region/{code}``

This endpoint will return news in a region.

Example: ``http://hq.vat-sea.com/api/news/region/SEA``

Retrieve news by division
""""""""""""""""""""

``http://hq.vat-sea.com/api/news/division/{code}``

This endpoint will return news in a division.

Example: ``http://hq.vat-sea.com/api/news/division/SEA``

Response::

    {
	  "subject": "VATSEA Member Protection Policy",
	  "content": "<p>The <strong>VATSEA Member Protection Policy</strong> will be enforced effective immediately. The Division Policy will be updated shortly to include&nbsp;this newly added regulation.</p>\n\n            <blockquote>\n            <p>With immediate effect, ALL VATSIM members and Virtual Area Control Centers (vACC) under the South East Asia Division (VATSEA) are prohibited to post, distribute or demonstrate any forms of political, racial and/or religious material in all official VATSIM channels.</p>\n            \n            <p>This includes social media platforms including but not limited to Facebook pages and groups, Discord and WhatsApp.</p>\n            \n            <p>Members who fail to comply with this regulation will be subjected to disciplinary action.</p>\n            </blockquote>\n            \n            <p>If you have any questions, kindly private message me on discord or drop me an email at <a href='mailto:isaactan.vatsea@gmail.com'>isaactan.vatsea@gmail.com</a></p>\n            \n            <p>Thank you for your attention</p>",
	  "created_by": "Web Four (10000004)"
    }

Retrieve news by vACC
""""""""""""""""

``http://hq.vat-sea.com/api/news/vacc/{code}``

This endpoint will return news in a vACC.

Example: ``http://hq.vat-sea.com/api/news/vacc/MYS``
   
======
Policy
======

Retrieve a policy
""""""""""""

``http://hq.vat-sea.com/api/policy/{id}``

This endpoint will return a policy.

Example: ``http://hq.vat-sea.com/api/policy/1``

Retrieve policy by region
""""""""""""""""""""

``http://hq.vat-sea.com/api/policy/region/{code}``

This endpoint will return policy in a region.

Example: ``http://hq.vat-sea.com/api/policy/region/APAC``

Retrieve policy by division
""""""""""""""""""""""

``http://hq.vat-sea.com/api/policy/division/{code}``

This endpoint will return policy in a division.

Example: ``http://hq.vat-sea.com/api/policy/division/SEA``

Retrieve policy by vACC
""""""""""""""""""

``http://hq.vat-sea.com/api/policy/vacc/{code}``

This endpoint will return policy in a vACC.

Example: ``http://hq.vat-sea.com/api/policy/vacc/MYS``

======
Region
======

Retrieve a region
""""""""""""

``http://hq.vat-sea.com/api/region/{code}``

This endpoint will return a region.

Example: ``http://hq.vat-sea.com/api/region/APAC``

Retrieve divisions in region
"""""""""""""""""""""""

``http://hq.vat-sea.com/api/region/{code}/division``

This endpoint will return division in the region.

Example: ``http://hq.vat-sea.com/api/region/APAC/division``

Retrieve region staff
""""""""""""""""

``http://hq.vat-sea.com/api/region/{code}/staff``

This endpoint will return staff in the region.

Example: ``http://hq.vat-sea.com/api/region/APAC/staff``
   
========
Division
========

Retrieve a division
""""""""""""""

``http://hq.vat-sea.com/api/division/{code}``

This endpoint will return a division.

Example: ``http://hq.vat-sea.com/api/division/SEA``

Retrieve vACC in division
""""""""""""""""""""

``http://hq.vat-sea.com/api/division/{code}/vacc``

This endpoint will return vACC in the division.

Example: ``http://hq.vat-sea.com/api/division/SEA/vacc``

Retrieve division staff
""""""""""""""""""

``http://hq.vat-sea.com/api/division/{code}/staff``

This endpoint will return staff in the division.

Example: ``http://hq.vat-sea.com/api/division/SEA/staff``

Retrieve division mentor
"""""""""""""""""""

``http://hq.vatwa.net/api/division/{code}/mentor``

This endpoint will return mentor of the division.

Example: ``http://hq.vatwa.net/api/division/WA/mentor``
   
====
vACC
====

Retrieve a vACC
""""""""""

``http://hq.vat-sea.com/api/vacc/{code}``

This endpoint will return a vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK``

Retrieve resident in vACC
""""""""""""""""""""

``http://hq.vat-sea.com/api/vacc/{code}/resident``

This endpoint will return residents in the vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK/resident``

Retrieve resident by rating in vACC
""""""""""""""""""""""""""""""

``http://hq.vat-sea.com/api/vacc/{code}/rating/{rating}``

This endpoint will return residents with the rating in the vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK/rating/3``

Retrieve visitor in vACC
"""""""""""""""""""

``http://hq.vat-sea.com/api/vacc/{code}/visitor``

This endpoint will return visitors in the vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK/visitor``

Retrieve vACC staff
""""""""""""""

``http://hq.vat-sea.com/api/vacc/{code}/staff``

This endpoint will return staff of the vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK/staff``

Retrieve vACC mentor
"""""""""""""""

``http://hq.vat-sea.com/api/vacc/{code}/mentor``

This endpoint will return mentor of the vACC.

Example: ``http://hq.vat-sea.com/api/vacc/HK/mentor``

   
====
Solo
====

Retrieve solo by region
""""""""""""""""""""

``http://hq.vat-sea.com/api/solo/region/{code}``

This endpoint will return solo in a region.

Example: ``http://hq.vat-sea.com/api/solo/region/APAC``

Retrieve solo by division
""""""""""""""""""""""

``http://hq.vat-sea.com/api/solo/division/{code}``

This endpoint will return solo in a division.

Example: ``http://hq.vat-sea.com/api/solo/division/SEA``

Retrieve solo by vACC
""""""""""""""""""

``http://hq.vat-sea.com/api/solo/vacc/{code}``

This endpoint will return solo in a vACC.

Example: ``http://hq.vat-sea.com/api/solo/vacc/MYS``

===========
CharSceCtor
===========

Retrieve CharSceCtor in vACC by type
"""""""""""""""""""""""""""""""

``http://hq.vat-sea.com/api/charscector/{code}/{type}``

This endpoint will return CharSceCtor in a vACC with mentioned type.

Available type: chart, misc, scenery, sop (all with lowercase, otherwise won't work)

Example: ``http://hq.vat-sea.com/api/charscector/VCL/chart``
