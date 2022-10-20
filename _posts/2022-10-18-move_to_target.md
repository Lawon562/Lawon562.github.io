---
title: 타겟으로 이동하는 방법
author: Lawon562
date: 2022-10-18
category: Movement
layout: post
---

<hr/>

## Player Object를 Target의 위치로 이동시키는 방법에 대해 알아본다.

![Player and Object Image](../assets/Movement/MoveToTarget/Title.png)

### 1) Set Position
<hr/>

<p>Player의 position vector를 Target의 position vector로 지정하는 방법.</p>

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Movement : MonoBehaviour
{
    public Transform target;

    void Update()
    {
        transform.position = target.position;
    }
}
```

![SetPosition_Unity](../assets/Movement/MoveToTarget/SetPosition1.png)

#### 실행 결과

<img src="../assets/Movement/MoveToTarget/SetPosition_result.gif" width="800px" height="400px" title="실행 결과" alt="실행 결과"/>

*Player Object를 선택하고 위치를 변경해보려고 하면, 변경되지 않는다. 대신 Target Object의 위치를 변경하면 동시에 Player의 위치도 같이 바뀐다.*
<hr/>


### 2) Lerp

<p>Player Object 위치와 Target의 위치를 백분율(t)만큼 선형 보간식으로 이동 시키는 방법</p>


```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Movement : MonoBehaviour
{
    public Transform target;
    public float t;


    void Update()
    {
        Vector3 a = transform.position;
        Vector3 b = target.position;
        transform.position = Vector3.Lerp(a, b, t);
    }
}
```

![Lerp1](../assets/Movement/MoveToTarget/Lerp1.png)

