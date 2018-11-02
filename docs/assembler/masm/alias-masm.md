---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: ab00092f410d34119e876db4562e6d0709743d79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483500"
---
# <a name="alias-masm"></a>ALIAS (MASM)

**エイリアス**ディレクティブは、関数の代替名を作成します。  これにより、関数に対して複数の名前を作成またはリンカー (LINK.exe) 古い関数を新しい関数にマップするライブラリを作成できます。

## <a name="syntax"></a>構文

> エイリアス\<*エイリアス*> = \<*実際の名前*>

#### <a name="parameters"></a>パラメーター

*実際の名前*<br/>
関数またはプロシージャの実際の名前。  山かっこは必要です。

*alias*<br/>
代替またはエイリアスの名前です。  山かっこは必要です。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>