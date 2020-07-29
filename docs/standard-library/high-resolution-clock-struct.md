---
title: high_resolution_clock struct |Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 850d5e3a5434aa44e23a7f74aeb9c306ab6c0a8e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203209"
---
# <a name="steady_clock-struct"></a>steady_clock 構造体

*High_resolution*クロックを表します。

## <a name="syntax"></a>構文

```cpp
class high_resolution_clock
```

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedefs

|名前|説明|
|----------|-----------------|
|`duration`|に `nanoseconds` 定義されているのシノニム \<chrono> 。|
|`period`|に `nano` 定義されているのシノニム \<ratio> 。|
|`rep`|**`long long`** のシノニム。含まれているのインスタンス化のクロックティック数を表すために使用される型 `duration` 。|
|`time_point`|`chrono::time_point<high_resolution_clock>` と同義。|

## <a name="functions"></a>関数

|||
|-|-|
|`now`|現在の時刻を値として返し `time_point` ます。|

## <a name="constants"></a>定数

|名前|説明|
|----------|-----------------|
|`is_steady`|**`true`** を保持します。 `high_resolution_clock` は*安定*しています。|
