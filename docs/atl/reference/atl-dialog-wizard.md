---
title: ATL ダイアログ ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2d78f0a41edca44f8841d701cc87975c551466
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358007"
---
# <a name="atl-dialog-wizard"></a>ATL ダイアログ ウィザード
このウィザードが、プロジェクトに、ATL ダイアログ ボックスから派生したオブジェクトを挿入[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)です。 ダイアログ ボックスから派生した`CAxDialogImpl`ActiveX コントロールをホストできます。  
  
 ウィザードは、既定値は、ダイアログ リソースを作成します**OK**と**キャンセル**ボタン。 ダイアログ リソースを編集し、ActiveX コントロールを使用してを追加することができます、[ダイアログ エディター](../../windows/dialog-editor.md)リソース ビューでします。  
  
 ヘッダー ファイルに挿入された、[メッセージ マップ](../../atl/message-maps-atl.md)既定値を処理するための宣言には、イベントが をクリックします。 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)ATL ダイアログ ボックスについての詳細。  
  
 **短い名前**  
 ATL ダイアログ オブジェクトの省略名を設定します。 指定した名前は、それらのフィールドを個別に変更していない限り、クラス名とファイル (.cpp、.h) 名を決定します。  
  
 `Class`  
 作成するクラスの名前を設定します。 この名前で指定した名前に基づきます**短い名前**、'C'、クラス名の一般的なプレフィックスが付きます。  
  
 **.h ファイル**  
 新しいオブジェクトのクラスのヘッダー ファイルの名前を設定します。 既定では、この名前は、名に基づいて内に指定した**短い名前**です。 ファイル名を任意の場所に保存するか、既存のファイルに、クラスの宣言を追加する、省略記号ボタンをクリックします。 既存のファイルを選択すると場合、ウィザードは保存されません、選択した場所にするまで をクリック**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラス宣言が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **.cpp ファイル**  
 新しいオブジェクトのクラスの実装ファイルの名前を設定します。 既定では、この名前は、名に基づいて内に指定した**短い名前**です。 ファイル名を任意の場所に保存する、省略記号ボタンをクリックします。 クリックするまで、選択した場所にファイルが保存されません**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラスの実装が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
## <a name="see-also"></a>関連項目  
 [ATL ダイアログ ボックス](../../atl/reference/adding-an-atl-dialog-box.md)

