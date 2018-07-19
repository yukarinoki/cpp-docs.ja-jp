---
title: steady_clock 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f4deb0bfe9439011f75cd22d0d52b74dae9c1f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959726"
---
# <a name="steadyclock-struct"></a>steady_clock 構造体

表す、*定常*クロック。

## <a name="syntax"></a>構文

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Remarks

Windows で`steady_clock`ラップ、`QueryPerformanceCounter`関数。

`now` への最初の呼び出しによって返される値が、`now` への以降の呼び出しによって返される値以下である場合、クロックは常に*単調*になります。 *単調*で、クロックのティック間の時間が一定のクロックは*安定しています*。

`high_resolution_clock` typedef は、`steady_clock`します。

### <a name="public-typedefs"></a>パブリック typedef

|name|説明|
|----------|-----------------|
|`steady_clock::duration`|シノニム`nanoseconds`で定義された\<chrono >。|
|`steady_clock::period`|シノニム`nano`で定義された\<ratio >。|
|`steady_clock::rep`|シノニム**長い****長い**に含まれているインスタンス化のクロック ティック数を表すために使用される型`duration`します。|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>` と同義。|

## <a name="public-functions"></a>パブリック関数

|関数|説明|
|--------------|-----------------|
|`now`|として現在の時刻を返します、`time_point`値。|

## <a name="public-constants"></a>パブリック定数

|name|説明|
|----------|-----------------|
|`steady_clock::is_steady`|保持している**true**します。 `steady_clock` は*安定*しています。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<chrono >

**名前空間:** std::chrono

## <a name="see-also"></a>関連項目

- [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 構造体](../standard-library/system-clock-structure.md)
