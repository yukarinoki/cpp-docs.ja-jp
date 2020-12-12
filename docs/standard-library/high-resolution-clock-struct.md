---
description: '詳細については、次を参照してください: high_resolution_clock 構造体'
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
ms.openlocfilehash: 2c5272413636e40dadf9201f684d32aaaa6708ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324055"
---
# <a name="high_resolution_clock-struct"></a>high_resolution_clock 構造体

*High_resolution* クロックを表します。

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

|名前|説明|
|-|-|
|`now`|現在の時刻を値として返し `time_point` ます。|

## <a name="constants"></a>定数

|名前|説明|
|----------|-----------------|
|`is_steady`|**`true`** を保持します。 `high_resolution_clock` は *安定* しています。|
