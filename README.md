> # 1. PROJECT DESCRIPTION
> ### About the company
> * Scentbird is a parfumes subscription service. Every month users get a small bottle (volume is 8ml) of perfume for $ 14.95. Each month the user will get another perfume for the same subscription price. They can test a lot of famous perfume brands and lines for the same price each month.

> ###  Task description
> * The User Acquisition team spends a lot of money for traffic purchasing. Constantly they test new user acquisition channels, ideas, discount offers etc.

> * One of the key metrics of traffic quality is a user lifetime - number of months, when a user has an active subscription. The user lifetime metric can be used to stop traffic purchasing if acquired users have very short lifetime and do not bring any value. From the other side, user lifetime reveals the most effective channels.

> * The aim of this work is to develop a model to predict whether the user will stop subscription during the first three months. The prediction model should use information collected in the first 48 hours after the subscription starts.

> * Because Scentbird is a subscription service, they do not have a lot of information about their users. Users do not interact with web-site/app very much - «subscribe and forget».

> ### Additional info about service:
> * Users queue – users can schedule a queue of perfumes. You can choose what you want to receive in the first month, second month … . There are users that are subscribing, filling queue for the next 12 months, leaving our website and not visiting it again for the next 12 months

> * Referral program – you may share a link to your friend. In case if your friend subscribes both of you will receive one month of subscription for free

> * Quiz – some of our users are participating in quiz which helps them to choose perfume/perfume style by answering simple questions

> * Upcharge – there are a few items that can’t be purchased with the standard plan (14.95 / month) and you need to pay extra 5$

> * Upgrade – our standard and most popular plan is 14.95$ / 1 item / Month but we also have other plans like (2 items per month, 3 items per month, yearly prepaid plan, 3 months prepaid plan … )

> * Skip month – you may skip next month if you don’t want a delivery (maybe you are still using previous perfume or just want to take a short break)

> ### Dataset description
> Dataset consists of 4 files:
> 1. Ya_practicum_good_users_info.csv – Properties of the users that have lifetime (measured in months) >= 3
> 1. Ya_practicum_bad_users_info.csv – Properties of the users that have lifetime (measured in months) < 3
> 1. Ya_practicum_ltv_bad_users_events_dataset.csv – Events log of the “bad” users
> 1. Ya_practicum_ltv_good_users_events_dataset.csv – Events log of the “good” users

> ### Ya_practicum_(good/bad)_users_info Subscription_hash – hashed subscription id (key)
> * Channel – marketing channel (Channel_1, Channel_2, Channel_3) defines marketing platform through which user has been acquired
> * First_month_price – subscription price for the first month (we usually give some discounts for first month)
> * Email_domain – hashed email domain of the user. For an example my_mail@msn.ru here “msn.ru” – email domain
> * First_payment_type – payment method which user used for his first transaction (Card, PayPal …)
> * Subscription_platform – web or app (platform of the first subscription)
> * Signup_platform – sers may sign up finishing payment flow that’s why signup_platform may differ from the subscription_platfrom
> * Fragrance_family – some of the users take quiz where we define fragrance family which is best for them
> * Scent_profile_title – another quiz related thing, users scent profile
> * Shipping_region – state
> * Shipping_city
> * Is_upgraded_in_first_2_days – True if user has upgraded in first 2 days (48 hours) after his subscription
> * Is_upcharged_in_first_2_days – True if uses has been upcharched in first 2 days (48 hours) after his subscription
> * Minutes_from_registration – minutes from users registration to his first subscription
> * Subscription_lifetime – amount of months from subscription purchase to unsubscribe (bad users have subscription_lifetime < 3, good users >= 3)
> * Age_tier – user’s age tier
> * Sex
> * income_tier – expected user’s income range

> ### Ya_practicum_(good/bad)_events_dataset
> * Subscription_hash – hashed subscription id (key)
> * Minutes_from_registration – diff in minutes from registration to event
> * Browser_name
> * browser_family
> * browser_type
> * browser_language
> * os_name
> * Event_name
> * AddToQueue – user added smth to his queue
> * LoginFailed
> * LoginSuccess
> * ReferralRegistration – If you invite your friend to use our service and he will register using link you provided to him then we will fire this event on your side
> * ReferralSubscriptionPurchase – If you invite your friend to use our service and he will buy a subscription using link you provided to him then we will fire this event on your side
> * RemoveFromQueue – deleting smth from queue
> * RestorePassword
> * SkipMonth – you may use this option if you don’t want receive a perfume in the next month
> * SubscriptionUpgrade – upgrading from current subscription plan. Our most popular plan – Monthly 1 pc, but you may upgrade for an example to Monthly 2 pcs (receiving 2 items in month)
> * Unsubscribe
> * Page_view – visiting page on our website
> * Amount_of_events – amount of current event during specified minute from registration. For an example if user has visited 3 different pages in one minute then there will be row with ....<event_name=page_view> <Amount_of_events=3>

>##  Libraries Used
> * Pandas
> * Matplotlib.pyplot
> * numpy
> * collections
> * sklearn
> * scipy
> * scikitplot
> * xgboost
> * lightgbm

>##  Models Evaluated
> * AdaBoostClassifier
> * XGBClassifier
> * LGBMClassifier
> * LogisticRegression
