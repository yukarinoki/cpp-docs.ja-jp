---
description: '詳細については、次を参照してください: steady_clock 構造体'
title: steady_clock 構造体
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 066a98f4eba6670e640e9fcc9b79eb017859a3d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169074"
---
# <a name="steady_clock-struct"></a>steady_clock 構造体

*定常* クロックを表します。

## <a name="syntax"></a>構文

```cpp
struct steady_clock;
```

## <a name="remarks"></a>解説

Windows では、 `steady_clock` 関数をラップし `QueryPerformanceCounter` ます。

`now` の最初の呼び出しによって返される値が、常に `now` の以降の呼び出しによって返される値以下である場合、クロックは *単調* になります。 *単調* で、クロックのティック間の時間が一定のクロックは *安定しています*。

`high_resolution_clock` はの typedef です `steady_clock` 。

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`steady_clock::duration`|に `nanoseconds` 定義されているのシノニム \<chrono> 。|
|`steady_clock::period`|に `nano` 定義されているのシノニム \<ratio> 。|
|`steady_clock::rep`|**`long long`** のシノニム。含まれているのインスタンス化のクロックティック数を表すために使用される型 `duration` 。|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>` と同義。|

## <a name="public-functions"></a>パブリック関数

|機能|説明|
|--------------|-----------------|
|`now`|現在の時刻を値として返し `time_point` ます。|

## <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|`steady_clock::is_steady`|**`true`** を保持します。 `steady_clock` は *安定* しています。|

## <a name="requirements"></a>要件

**ヘッダー:**\<chrono>

**名前空間:** std::chrono

## <a name="see-also"></a>関連項目

- [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 構造体](../standard-library/system-clock-structure.md)
