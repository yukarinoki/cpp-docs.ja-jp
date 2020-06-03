---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: ba1377359ba9bc960e5d7d2a55df15adfe0d5d33
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076223"
---
# <a name="invoke"></a>INVOKE

(32 ビット MASM のみ。)*式*によって指定されたアドレスでプロシージャを呼び出し、言語の種類の標準の呼び出し規約に従って、スタックまたはレジスタの引数を渡します。

## <a name="syntax"></a>構文

> **呼び出し***式*⟦ __、__ *引数*...⟧

## <a name="remarks"></a>解説

プロシージャに渡される各引数には、式、レジスタペア、またはアドレス式 ( **ADDR**で始まる式) を指定できます。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
