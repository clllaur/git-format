---
title: Introduction
excerpt: >-
  The official JavaScript SDK for integrating Convert.com's Fullstack
  experimentation platform
---
# Introduction

<br />

The official JavaScript SDK for integrating Convert.com's Fullstack experimentation platform. Run A/B tests, feature flags, and feature rollouts in Node.js and browser environments.

<br />

## Quick Install

<br />

````
bash

npm install --save @convertcom/js-sdk

```



## Key Features



- **A/B Testing** — Run experiments to optimize user experience with statistical significance tracking

- **Feature Flags** — Control feature releases with precision. Enable or disable features for specific users

- **Feature Rollouts** — Gradually release features to percentages of your user base with full control

- **Audience Targeting** — Target specific user segments based on properties, behaviors, and custom rules



## Simple Integration



Get up and running with just a few lines of code:



```typescript

import ConvertSDK from '@convertcom/js-sdk';



const convertSDK = new ConvertSDK({

  sdkKey: 'your-sdk-key',

  environment: 'production'

});



await convertSDK.onReady();



const context = convertSDK.createContext('user-123');

const feature = context.runFeature('new-checkout');



if (feature?.status === 'enabled') {

  // Show new checkout experience

}

```



## SDK Architecture



The SDK is built from specialized modules that work together:



| Module | Role |

| --- | --- |

| **ConvertSDK / Core** | Main entry point — initializes all managers, fetches configuration, creates visitor contexts |

| **Context** | Per-visitor session object — runs experiments, checks features, tracks conversions |

| **ExperienceManager** | Manages A/B tests — selects variations for visitors via DataManager |

| **FeatureManager** | Controls feature flags — checks if features are enabled for visitors |

| **DataManager** | Central data hub — stores configuration, visitor state, and orchestrates bucketing |

| **BucketingManager** | Assigns visitors to variations — uses deterministic hashing for fair, consistent splits |

| **RuleManager** | Evaluates targeting rules — checks if visitors meet audience/segment criteria |

| **ApiManager** | Handles API communication — fetches config and sends tracking events in batches |

| **EventManager** | Internal pub/sub system — fires events like READY, BUCKETING, CONVERSION |



For detailed documentation on each module, see the Core Modules section.



## Supported Platforms



The SDK supports both **Node.js** and **browser** environments:



| Platform | Minimum Version |

| --- | --- |

| Node.js | v14.0.0 or later |

| Browser | All modern browsers (Chrome, Firefox, Safari, Edge) |



## Resources



- [GitHub Repository](https://github.com/convertcom/javascript-sdk) — Source code and issue tracker

- [Convert.com](https://www.convert.com/) — Main product website

- [Apache-2.0 License](https://choosealicense.com/licenses/apache-2.0/) — Open source license



## Next Steps



Head to the Installation section to get started. For an in-depth understanding of the SDK internals, explore the Core Modules documentation.
````
