## Wishbook Product

A little bit of introduction to Wishbook is in [this slidedeck](https://drive.google.com/file/d/1I_fcIl8HzRljOVIWALxbv1DYKUO4NHca/view?usp=sharing) (including why it [scaled operations down](https://arvindsaraf.medium.com/note-to-wishbook-users-why-we-scaled-down-13280a3140)). The product offering is described in [this doc](https://drive.google.com/file/d/1XFCfX0CTbrHdXT15xZPywSSMQf78BObO/view?usp=sharing), along with a [note on why this is now open-sourced](https://arvindsaraf.medium.com/open-sourcing-wishbook-66464871128d).

## Repositories

This codebase consists of the following repos:
- [android-app](https://github.com/wishbook-io/android-app): The native android app that the buyers & sellers mostly used. This covered the full buyer functionality & significant part of the seller functionality. More power seller functionality was in the webapp repo.
- [reactnative-app](https://github.com/wishbook-io/reactnative-app): The reactnative version was on the way to be the single app code base that ran on iOS, android & browser lite. While lagging in some features (due to the parallel development), this was live on iOS & browser lite till the development paused (~Sep 2019).
- [webapps](https://github.com/wishbook-io/webapps): Set of web apps, with largely shared code base that covers the Seller Panel & Super Admin (ie internal platform admin) functionality.
- [backend](https://github.com/wishbook-io/backend): Django backed with APIs & celery based background tasks.
- [appium-tests](https://github.com/wishbook-io/appium-tests) Exhaustive appium based test suite for the mobile app. Attempt made to keep the same identifiers in the Android & ReactNative apps so that the suite works across both.

## Performance, Disclaimers

The setup work started in 2016 & hence ran on the state of the art then - ie on a few VMs (not dockerized, kubernetized). The Get APIs were cached at the Nginx level, and the MySQL had fine tuned query caching. These settings are not part of the repo. At it’s peak, a single database on a 8 node VM & a single API frontend on a smaller VM could serve about 10K daily active users.

The code is not reviewed, lacks unit tests, and the variables may not be factored out. It is not currently being maintained. 
