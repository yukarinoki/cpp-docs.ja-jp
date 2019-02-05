---
title: _CIexp
ms.date: 11/04/2016
apiname:
- _CIexp
apilocation:
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CIexp
- _CIexp
helpviewer_keywords:
- CIexp intrinsic
- _CIexp intrinsic
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
ms.openlocfilehash: fa608af9406dc03047ff9f113ac648e215b0d117
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703286"
---
# <a name="ciexp"></a>_CIexp

スタックのトップ値の指数を計算します。

## <a name="syntax"></a>構文

```
void __cdecl _CIexp();
```

## <a name="remarks"></a>コメント

このバージョンの `exp` 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、スタックのトップにプッシュされます。

## <a name="requirements"></a>要件

**プラットフォーム:** x86

## <a name="see-also"></a>「

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[exp、expf、expl](../c-runtime-library/reference/exp-expf.md)