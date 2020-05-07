---
title: _CIcos
ms.date: 4/2/2020
api_name:
- _CIcos
- _o__CIcos
api_location:
- msvcr90.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIcos
- _CIcos
helpviewer_keywords:
- _CIcos intrinsic
- CIcos intrinsic
ms.assetid: 6fc203fb-66f3-4ead-9784-f85833c26f1b
ms.openlocfilehash: a9b18c2eb0a76885f3c3aad7bb1f03d7dea52c5c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918067"
---
# <a name="_cicos"></a>_CIcos

浮動小数点スタックのトップ値のコサインを計算します。

## <a name="syntax"></a>構文

```C
void __cdecl _CIcos();
```

## <a name="remarks"></a>解説

このバージョンの [cos](../c-runtime-library/reference/cos-cosf-cosl.md) 関数には、コンパイラで認識される特殊な呼び出し規則があります。 コピーの生成を防ぎ、レジスタ割り当てが容易になるため、実行時間が短縮されます。

結果の値は、浮動小数点スタックのトップにプッシュされます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

**プラットフォーム:** x86

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[cos、cosf、cosl](../c-runtime-library/reference/cos-cosf-cosl.md)<br/>
