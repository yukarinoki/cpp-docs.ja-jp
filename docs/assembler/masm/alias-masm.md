---
title: エイリアス (MASM) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 7b14e1c41a448d0cb7014dabc50a42305249938f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049168"
---
# <a name="alias-masm"></a>ALIAS (MASM)
**エイリアス**ディレクティブによって、関数の代替名を作成します。  これにより、関数に対して複数の名前を作成またはリンカー (LINK.exe) を新しい関数には古い関数にマップするライブラリを作成できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `actual-name`  
 関数またはプロシージャの実際の名前。  山かっこは必要があります。  
  
 `alias`  
 代替またはエイリアスの名前です。  山かっこは必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)