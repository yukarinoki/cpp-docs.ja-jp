---
title: ALIAS (MASM) |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Alias
dev_langs:
- C++
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6a977d35040d8ca25cd3bd4ae4def233092b37a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691063"
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