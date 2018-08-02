---
title: ATL の定義済みのシンボル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols, ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 098ce812b18e64409e24d58675144f2c660bcdd7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465650"
---
# <a name="atl-predefined-symbols"></a>ATL の定義済みシンボル
これらのシンボルは、ATL ヘッダー ファイルで定義されているが、標準の Windows アプリケーションの関数とアクションをサポートします。 これらのシンボルは、ダイアログ ボックスが主に使用されます。 ダイアログとコントロールを使用する場合に、[ダイアログ エディター](../windows/dialog-editor.md)にこれらのシンボルが表示されます、**プロパティ**コモン コントロールに関連付けられているウィンドウ。 たとえば、ダイアログ ボックスがある場合、**キャンセル**ボタン、コマンドは IDCANCEL シンボルに関連付けられますことで、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)。  
  
|||  
|-|-|  
|IDABORT|コントロール: ダイアログ ボックスの [中止] ボタン|  
|IDC_STATIC|スタティック コントロールの制御:|  
|IDCANCEL|制御: ダイアログ ボックスの [キャンセル] ボタン|  
|IDIGNORE|制御: ダイアログ ボックス [無視] ボタン|  
|IDNO|制御: ダイアログ ボックスの [いいえ] ボタン|  
|IDOK|コントロール: ダイアログ ボックスの [OK] ボタン|  
|IDR_ACCELERATOR1|アクセラレータ テーブルなリソース:|  
|IDRETRY|制御: ダイアログ ボックスの [再試行] ボタン|  
|IDS_PROJNAME|現在のアプリケーション名を文字列:|  
|IDYES|制御: ダイアログ ボックスの はい ボタンします。|  
  
## <a name="requirements"></a>要件  
 ATL  
  
## <a name="see-also"></a>関連項目  
 [定義済みシンボル Id](../windows/predefined-symbol-ids.md)   
 [シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)