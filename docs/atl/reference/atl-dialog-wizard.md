---
title: ATL ダイアログ ウィザード |Microsoft Docs
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
ms.openlocfilehash: 8a10d97d366203da8addbff45a436094abc384cb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710126"
---
# <a name="atl-dialog-wizard"></a>ATL ダイアログ ウィザード

このウィザードから派生した、ATL ダイアログ ボックス オブジェクトをプロジェクトに挿入[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)します。 ダイアログ ボックスから派生した`CAxDialogImpl`ActiveX コントロールをホストできます。

ウィザードでは、ダイアログ リソースを作成、既定値は**OK**と**キャンセル**ボタン。 ダイアログ リソースを編集して追加の ActiveX コントロールを使用して、[ダイアログ エディター](../../windows/dialog-editor.md)リソース ビューで。

ヘッダー ファイルに挿入された、[メッセージ マップ](../../atl/message-maps-atl.md)既定値を処理するための宣言がイベントをクリックします。 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)ATL ダイアログ ボックスの詳細についてはします。

- **短い名前**

   ATL ダイアログ オブジェクトの省略名を設定します。 指定した名前では、これらのフィールドを個別に変更しない限り、クラス名とファイル (.cpp、.h) 名を決定します。

- **クラス**

   作成するクラスの名前を設定します。 この名前がで指定した名前に基づいて**短い名前**'C'、クラス名の一般的なプレフィックスが付いた、します。

- **.h ファイル**

   新しいオブジェクトのクラスにヘッダー ファイルの名前を設定します。 既定では、この名前がで指定した名前に基づくは**短い名前**します。 選択した場所にファイル名を保存するには、あるいはクラス宣言を既存のファイルに追加するには、省略記号ボタンをクリックします。 既存のファイルを選択した場合、ウィザードで **[完了]** をクリックするまで、ファイルは選択した場所に保存されません。

   ウィザードではファイルは上書きされません。 既存のファイルの名前を選択する場合、**[完了]** をクリックすると、ウィザードからクラス宣言をファイルのコンテンツに追加するかどうかを指定するように求められます。 ファイルを追加するには、**[はい]** をクリックします。ウィザードに戻り、別のファイル名を指定するには、**[いいえ]** をクリックします。

- **.cpp ファイル**

   新しいオブジェクトのクラスに実装ファイルの名前を設定します。 既定では、この名前がで指定した名前に基づくは**短い名前**します。 ファイル名を選択した場所に保存するには、省略記号ボタンをクリックします。 ファイルは、ウィザードで **[完了]** をクリックするまで選択した場所に保存されません。

   ウィザードではファイルは上書きされません。 既存のファイルの名前を選択する場合、**[完了]** をクリックすると、ウィザードからクラスの実装をファイルのコンテンツに追加するかどうかを指定するように求められます。 ファイルを追加するには、**[はい]** をクリックします。ウィザードに戻り、別のファイル名を指定するには、**[いいえ]** をクリックします。

## <a name="see-also"></a>関連項目

[ATL ダイアログ ボックス](../../atl/reference/adding-an-atl-dialog-box.md)

