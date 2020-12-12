---
description: '詳細については、次を参照してください: _CIfmod'
title: _CIfmod
ms.date: 4/2/2020
api_name:
- _CIfmod
- _o__CIfmod
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIfmod
- CIfmod
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
ms.openlocfilehash: db5ebb6178b468d9f131c374c8ef128a90664d17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246982"
---
# <a name="_cifmod"></a>_CIfmod

スタックの 2 つのトップ値の浮動小数点の剰余を計算します。

## <a name="syntax"></a>構文

```cpp
void __cdecl _CIfmod();
```

## <a name="remarks"></a>解説

このバージョンの `fmod` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、スタックのトップにプッシュされます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>要件

**プラットフォーム:** x86

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[fmod、fmodf](../c-runtime-library/reference/fmod-fmodf.md)
