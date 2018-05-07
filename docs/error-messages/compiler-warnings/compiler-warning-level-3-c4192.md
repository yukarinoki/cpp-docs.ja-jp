---
title: コンパイラの警告 (レベル 3) C4192 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3bae9b7af95de94b8f667cb09710af21044f8b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192
タイプ ライブラリ 'library' のインポート中に 'name' を自動的に除外  
  
 A`#import`ライブラリには、項目が含まれています*名前*、つまりも Win32 システム ヘッダーで定義します。 などの制限によりタイプ ライブラリの名**IUnknown** GUID は、多くの場合で定義されているタイプ ライブラリでは、システム ヘッダーの定義を複製します。 `#import` これらの項目を検出し、.tlh ファイルと .tli ヘッダー ファイルに組み込むことを拒否します。  
  
 この動作をオーバーライドするには使用`#import`属性[no_auto_exclude](../../preprocessor/no-auto-exclude.md)と[include()](../../preprocessor/include-parens.md)です。