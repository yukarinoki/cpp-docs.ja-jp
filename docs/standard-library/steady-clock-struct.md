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
ms.openlocfilehash: 5445379597c4fefcd657303a05c33b6509d54d2e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569899"
---
# <a name="steadyclock-struct"></a>steady_clock 構造体

表す、*定常*クロック。

## <a name="syntax"></a>構文

```cpp
struct steady_clock;
```

## <a name="remarks"></a>コメント

Windows では、`steady_clock`ラップ、`QueryPerformanceCounter`関数。

`now` への最初の呼び出しによって返される値が、`now` への以降の呼び出しによって返される値以下である場合、クロックは常に*単調*になります。 *単調*で、クロックのティック間の時間が一定のクロックは*安定しています*。

`high_resolution_clock` typedef`steady_clock`です。

### <a name="public-typedefs"></a>パブリック typedef

|name|説明|
|----------|-----------------|
|`steady_clock::duration`|シノニム`nanoseconds`で定義されている\<chrono >。|
|`steady_clock::period`|シノニム`nano`で定義されている\<比 >。|
|`steady_clock::rep`|シノニム**長い****長い**、包含をインスタンス化のクロック ティック数を表すために使用する型`duration`です。|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>` と同義。|

## <a name="public-functions"></a>パブリック関数

|関数|説明|
|--------------|-----------------|
|`now`|現在の時刻としてを返します、`time_point`値。|

## <a name="public-constants"></a>パブリック定数

|name|説明|
|----------|-----------------|
|`steady_clock::is_steady`|`true` を保持します。 `steady_clock` は*安定*しています。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<chrono >

**名前空間:** std::chrono

## <a name="see-also"></a>関連項目

- [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 構造体](../standard-library/system-clock-structure.md)
