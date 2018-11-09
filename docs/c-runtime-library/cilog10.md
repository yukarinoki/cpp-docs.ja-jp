---
title: _CIlog10
ms.date: 11/04/2016
apiname:
- _CIlog10
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- CIlog10
- _CIlog10
helpviewer_keywords:
- _CIlog10 intrinsic
- CIlog10 intrinsic
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
ms.openlocfilehash: 29052a2398186bb8ac39ba6e3361c9cbc977f8b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646106"
---
# <a name="cilog10"></a>_CIlog10

スタックのトップ値に対して `log10` 演算を実行します。

## <a name="syntax"></a>構文

```
void __cdecl _CIlog10();
```

## <a name="remarks"></a>コメント

このバージョンの `log10` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 この関数は、コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、スタックのトップにプッシュされます。

## <a name="requirements"></a>必要条件

**プラットフォーム:** x86

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[log、logf、log10、log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)