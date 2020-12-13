---
description: '詳細情報: INVOKE'
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: eb372ad3d7ccde9f217f55ed9817acfe9bd8f1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129845"
---
# <a name="invoke"></a>INVOKE

(32 ビット MASM のみ。) *式* によって指定されたアドレスでプロシージャを呼び出し、言語の種類の標準の呼び出し規約に従って、スタックまたはレジスタの引数を渡します。

## <a name="syntax"></a>構文

> **呼び出し***式*⟦__、__ *引数*...⟧

## <a name="remarks"></a>解説

プロシージャに渡される各引数には、式、レジスタペア、またはアドレス式 ( **ADDR** で始まる式) を指定できます。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
