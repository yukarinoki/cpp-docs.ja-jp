---
title: ルールの定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8ff7c58033ac5f7e42764d185c45c206bf406f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367122"
---
# <a name="defining-a-rule"></a>規則の定義
*Fromext*依存ファイルの拡張機能を表すと*toext*ターゲット ファイルの拡張機能を表します。  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>コメント  
 拡張機能は、大文字小文字を区別はありません。 表すマクロを呼び出すことができます*fromext*と*toext*; マクロはプリプロセッサによって展開されます。 ピリオド (.) 前*fromext*行の先頭に置く必要があります。 コロン (:) は、0 個以上のスペースまたはタブに続きます。 これは、スペースまたはタブ、コマンドを指定する、セミコロン (;)、コメントを指定するシャープ記号 (#) または復帰改行文字によってのみ実行できます。 他のスペースは許可されません。 コマンドは、記述ブロックのように指定します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [規則の検索パス](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>関連項目  
 [推論規則](../build/inference-rules.md)