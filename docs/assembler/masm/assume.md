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
ms.openlocfilehash: 6fbba50e56ae06dc3afb64582d4a131bba75a6c8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055854"
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