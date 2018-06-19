---
title: リンカ ツール エラー LNK2039 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 954ea12eb9b49c2bdf59b31a1ec2ec2e66c124ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302098"
---
# <a name="linker-tools-error-lnk2039"></a>リンカ ツール エラー LNK2039
ref クラスをインポートする\<型 >' another.obj で定義されている以外の場合は、インポートまたは定義されており、両方は使用できませんである必要があります  
  
 Ref クラス ' <`type`>' は、指定された .obj ファイルにインポートしますが、別の .obj ファイルにも定義されています。 この条件の実行時エラーまたはその他の予期しない動作が発生することができます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  確認するかどうか '`type`'、その他の .obj ファイルで定義する必要があります、.winmd ファイルからインポートする必要があるかどうかを確認します。  
  
2.  定義と、インポートのいずれかを削除します。  
  
## <a name="see-also"></a>関連項目  
 [リンカ ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [リンカー ツール エラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)