---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 4bf8f0c41e9ce3e296cf201efd4fd9be2033cbdb
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73702464"
---
# <a name="assume-32-bit-masm"></a>想定 (32 ビット MASM)

レジスタ値のエラーチェックを有効にします。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> *Segregister*:*name* [, *segregister*:*name*]]...<br/>
> *Dataregister*を想定:*type* [[, *dataregister*:*type*]]...<br/>
> ASSUME *register*: エラー [、*登録*: エラー].<br/>
> ASSUME [[*register*:]] 何も [、*登録*: 何も]

## <a name="remarks"></a>Remarks

`ASSUME` が有効になると、アセンブラーは、指定されたレジスタの値に対する変更を監視します。 レジスタが使用されている場合、**ERROR**によってエラーが生成されます。 レジスタエラーチェックは何も削除され**NOTHING**。 1つのステートメントでさまざまな種類の仮定を組み合わせることができます。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>