---
title: _CIsin
ms.date: 04/10/2018
apiname:
- _CIsin
apilocation:
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- CIsin
- _CIsin
helpviewer_keywords:
- _CIsin intrinsic
- CIsin intrinsic
ms.assetid: f215f39a-2341-4f1c-ba8e-cb522451ceb2
ms.openlocfilehash: 89350cdc61b7c96b09242731f89c934727e44a19
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481305"
---
# <a name="cisin"></a>_CIsin

浮動小数点スタックのトップ値のサインを計算します。

## <a name="syntax"></a>構文

```C
void __cdecl _CIsin();
```

## <a name="remarks"></a>コメント

この組み込みバージョンの [sin](../c-runtime-library/reference/sin-sinf-sinl.md) 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、浮動小数点スタックのトップにプッシュされます。

## <a name="requirements"></a>必要条件

**プラットフォーム:** x86

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sin、sinf、sinl](../c-runtime-library/reference/sin-sinf-sinl.md)<br/>
