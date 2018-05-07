---
title: コマンドラインの警告 D9041 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c22573d26e09e14789f4cbd64d68f4082125c2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9041"></a>コマンド ラインの警告 D9041
無効な値 'value' の '/option';'value'; と仮定した場合追加 '/analyze ' をこの警告を指定するときのコマンド ライン オプション  
  
 コード分析の警告番号が追加、 **/wd**、 **/we**、 **/wo**、または **/wl** を指定せずにコマンドラインオプション **/analyze**コマンド ライン オプションです。 このエラーを解決するを追加するか、 **/analyze**コマンド ライン オプション、または、適切なから無効な警告番号を削除する **/w**コマンド ライン オプションです。  
  
## <a name="example"></a>例  
 次のコマンドラインの例では、警告 D9041 が生成されます。  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 この警告を解決するには、するには追加、 **/analyze**コマンド ライン オプションです。 場合 **/analyze**はから無効な警告番号を削除するコンパイラのバージョンでサポートされていない、 **/wd**オプション。  
  
## <a name="see-also"></a>関連項目  
 [コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)