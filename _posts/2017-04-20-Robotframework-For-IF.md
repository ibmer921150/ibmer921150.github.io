---
layout: post
title: Robotframework For and IF/Else
category: robotframework
tags: [automation, robotframework]
---

## Robotframework Loop and Condition

### For

```
: FOR    ${I}    IN RANGE    3
    \    Log    ${i}
    \    ${LATEST}=    Wait for Email    status=UNSEEN    timeout=150
    \    ${parts}=    Walk Multipart Email    ${LATEST}
    \    ${body}    Get Email Body    ${LATEST}
    \    ${from}    Get Multipart Field    From
    \    ${to}    Get Multipart Field    To
    \    ${subject}    Get Multipart Field    Subject
    \    ${date}    Get Multipart Field    Date
    \    Exit For Loop If    ${i} == 2
```
### If/Else


        Run Keyword If    '${subject}' == 'xxx'    Should Contain    ${body}    xxx
        ...    ELSE IF    '${subject}' == 'xxx'
        ...    Run Keywords
        ...    Should Contain    ${body}    xxx
        ...    AND    Should Contain    ${to}    xxx
        ...    ELSE IF    '${subject}' == 'xxx'    Should Contain    ${body}    xxx
        ...    ELSE    Should Contain    ${body}    xxx
        Exit For Loop If    ${i} == 2