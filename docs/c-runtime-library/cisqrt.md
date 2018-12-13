---
title: _CIsqrt
ms.date: 11/04/2016
apiname:
- _CIsqrt
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _CIsqrt
- CIsqrt
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
ms.openlocfilehash: 25df1641ff839a77792f5a465d72e578b5d0f405
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453769"
---
# <a name="cisqrt"></a>_CIsqrt

スタックのトップ値の平方根を計算します。

## <a name="syntax"></a>構文

```
void __cdecl _CIsqrt();
```

## <a name="remarks"></a>コメント

このバージョンの `sqrt` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、スタックのトップにプッシュされます。

## <a name="requirements"></a>必要条件

**プラットフォーム:** x86

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sqrt、sqrtf、sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)