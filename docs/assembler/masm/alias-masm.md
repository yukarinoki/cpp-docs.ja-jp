---
description: '詳細情報: ALIAS'
title: ALIAS (MASM)
ms.date: 12/17/2019
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 7d5072cec8ef56f3dd2202617b3274c958a25d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121759"
---
# <a name="alias"></a>ALIAS

**ALIAS** ディレクティブは、関数の代替名を作成します。  これにより、関数に対して複数の名前を作成したり、リンカー (LINK.exe) が古い関数を新しい関数にマップできるようにするライブラリを作成したりすることができます。

## <a name="syntax"></a>構文

> **エイリアス \<**_alias_**> = \<**_actual-name_**>**

#### <a name="parameters"></a>パラメーター

*実際の名前*\
関数またはプロシージャの実際の名前。  山かっこが必要です。

*エイリアス*\
代替名または別名。  山かっこが必要です。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
