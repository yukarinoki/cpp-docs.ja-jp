---
title: コントロール プロパティの編集
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
ms.openlocfilehash: cd9226e6eb4fc2b16d24cd0c9727d4fcbfdbf02b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454805"
---
# <a name="editing-control-properties"></a>コントロール プロパティの編集

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>コントロールまたはコントロールのプロパティを編集するには

1. ダイアログ ボックスで、変更するコントロールを選択します。

   > [!NOTE]
   > 複数のコントロールを選択した場合は、選択したコントロールの共通プロパティのみを編集できます。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)コントロールのプロパティを変更します。

   > [!NOTE]
   > 設定すると、**ビットマップ**ボタン、オプション ボタン、またはチェック ボックス コントロールと同じプロパティを**True**BS_BITMAP の実装は、コントロールのスタイル。 詳細については、次を参照してください。[ボタンのスタイル](../mfc/reference/styles-used-by-mfc.md#button-styles)します。 コントロールとビットマップの関連付けの例は、次を参照してください。 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)します。 は、ビットマップは、コントロールに表示されません、**ダイアログ**リソース エディター。

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>コントロールのプロパティの変更を元に戻す

1. コントロールにフォーカスがあるかどうかを確認、**ダイアログ**エディター。

2. 選択**を元に戻す**から、**編集**メニュー (コントロールにフォーカスがない場合、**を元に戻す**コマンドは使用できません)。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)