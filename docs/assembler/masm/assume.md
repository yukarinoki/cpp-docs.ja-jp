---
title: 前提としています |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0e43548292d2ffecbebdaead6aa12d6dacc352
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693809"
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