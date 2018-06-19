---
title: コントロールのプロパティを編集 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f7976f74e9454b023c4da51168fa780ccaea2342
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873486"
---
# <a name="editing-control-properties"></a>コントロール プロパティの編集
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>以上のコントロールのプロパティを編集するには  
  
1.  ダイアログ ボックスで、変更するコントロールを選択します。  
  
    > [!NOTE]
    >  複数のコントロールを選択した場合は、選択したコントロールに共通するプロパティのみを編集できます。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)コントロールのプロパティを変更します。  
  
    > [!NOTE]
    >  設定すると、**ビットマップ**ボタン、オプション ボタンまたはチェック ボックス コントロールと同じプロパティを**True**BS_BITMAP がコントロールの実装のスタイル。 詳細については、次を参照してください。[ボタン スタイル](../mfc/reference/styles-used-by-mfc.md#button-styles)です。 コントロールとビットマップの関連付けの例は、次を参照してください。 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)です。 ビットマップは、ダイアログ リソース エディターでは、コントロールは表示されません。  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>コントロールのプロパティへの変更を元に戻す  
  
1.  ダイアログ エディターで、コントロールにフォーカスがあることを確認してください。  
  
2.  選択**を元に戻す**から、**編集**メニュー (フォーカスがコントロール上にない場合、**を元に戻す**コマンドは使用できません)。  
  
 マネージ プロジェクトにリソースを追加する方法については、次を参照してください。[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 」および「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)

