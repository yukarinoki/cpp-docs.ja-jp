---
description: '詳細については、次を参照してください: _CIsqrt'
title: _CIsqrt
ms.date: 4/2/2020
api_name:
- _CIsqrt
- _o__CIsqrt
api_location:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIsqrt
- CIsqrt
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
ms.openlocfilehash: b643ad301acc217f3fac1bbf1aeee1d7141702a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209621"
---
# <a name="_cisqrt"></a>_CIsqrt

スタックのトップ値の平方根を計算します。

## <a name="syntax"></a>構文

```cpp
void __cdecl _CIsqrt();
```

## <a name="remarks"></a>解説

このバージョンの `sqrt` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、スタックのトップにプッシュされます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>要件

**プラットフォーム:** x86

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sqrt、sqrtf、sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)
