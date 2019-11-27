---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 274ac451005015b2693d8674673af574ec781bdc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399292"
---
# <a name="alias-masm"></a>ALIAS (MASM)

**ALIAS**ディレクティブは、関数の代替名を作成します。  これにより、関数に対して複数の名前を作成したり、リンカー (convert.exe) が古い関数を新しい関数にマップできるようにするライブラリを作成したりできます。

## <a name="syntax"></a>構文

> **エイリアス \<** _エイリアス_ **> = \<** _実際の名前_ **>**

#### <a name="parameters"></a>パラメーター

*実際の名前*\
関数またはプロシージャの実際の名前。  山かっこが必要です。

*エイリアス*\
代替名または別名。  山かっこが必要です。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)
