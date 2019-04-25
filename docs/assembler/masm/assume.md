---
title: ASSUME
ms.date: 08/30/2018
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 97a57cc8a1acccf70572ff963e496aa79fa3ab43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166465"
---
# <a name="assume"></a>ASSUME

レジスタの値のエラー チェックを有効にします。

## <a name="syntax"></a>構文

> ASSUME *segregister*:*名前*[、 *segregister*:*名前*].<br/>
> ASSUME *dataregister*:*型*[、 *dataregister*:*型*].<br/>
> ASSUME*登録*: エラー [、*登録*: エラー].<br/>
> ASSUME [*登録*:] 何も [、*登録*: 何も].

## <a name="remarks"></a>Remarks

後に、`ASSUME`が有効になる、アセンブラーは、特定のレジスタの値に対する変更を監視します。 **エラー**レジスタが使用されている場合、エラーが発生します。 **何も**削除がエラー チェックを登録します。 さまざまな種類の 1 つのステートメントでの前提条件を組み合わせることができます。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>