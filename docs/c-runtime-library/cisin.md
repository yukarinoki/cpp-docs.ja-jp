---
title: _CIsin | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
helpviewer_keywords:
- _CIsin intrinsic
- CIsin intrinsic
ms.assetid: f215f39a-2341-4f1c-ba8e-cb522451ceb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4593b02b08b1828ff4b29c8f55bfcaf4baa0c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
