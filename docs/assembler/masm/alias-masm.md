---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: ab00092f410d34119e876db4562e6d0709743d79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166491"
---
# <a name="alias-masm"></a>ALIAS (MASM)

**ALIAS**ディレクティブは、関数の代替名を作成します。  これにより、関数に対して複数の名前を作成またはリンカー (LINK.exe) 古い関数を新しい関数にマップするライブラリを作成できます。

## <a name="syntax"></a>構文

> ALIAS \<*alias*> = \<*actual-name*>

#### <a name="parameters"></a>パラメーター

*actual-name*<br/>
関数またはプロシージャの実際の名前。  山かっこは必要です。

*alias*<br/>
代替またはエイリアスの名前です。  山かっこは必要です。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>