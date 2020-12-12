---
description: '詳細情報: 仮定'
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: b597e50dafe07950d87cb04cf5e697b63c55611c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121746"
---
# <a name="assume"></a>ASSUME

レジスタ値のエラーチェックを有効にします。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> *Segregister*__:__*name* ⟦__,__ *segregister*__:__*name*...⟧\  
> 次のように *dataregister*__:__*type* ⟦__,__ *dataregister*__:__*type*...⟧\  
> *レジスタ*__: error__ ⟦__、__ *register*__: error__...⟧\  
> **⟦** *Register*__:__⟧**NOTHING** ⟦__、__ *register*__: nothing__...⟧

## <a name="remarks"></a>解説

が有効になる **と** 、アセンブラーは、指定されたレジスタの値に対する変更を監視します。 レジスタが使用されている場合、**エラー** によってエラーが生成されます。 レジスタエラーチェックは何も削除され **ません**。 1つのステートメントでさまざまな種類の仮定を組み合わせることができます。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
