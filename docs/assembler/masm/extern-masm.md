---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 30d1b3ae7c6676aeb97b91c7627da859525b9ce1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203616"
---
# <a name="extern-masm"></a>EXTERN (MASM)

1 つまたは複数の外部変数、ラベル、または記号と呼ばれる定義*名前*型が*型*します。

## <a name="syntax"></a>構文

> EXTERN [[*langtype*]] *name* [[ (*altid*) ]] : *type* [[, [[*langtype*]] *name* [[ (*altid*) ]] : *type*]] ...

## <a name="remarks"></a>Remarks

*型*できる[ABS](../../assembler/masm/operator-abs.md)、どの imports*名前*定数として。 同じ[EXTRN](../../assembler/masm/extrn.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>