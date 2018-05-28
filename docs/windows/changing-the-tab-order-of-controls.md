---
title: コントロールのタブ オーダーの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33e6e9624e7e927860a184361d45f855f3a1e4f6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-tab-order-of-controls"></a>コントロールのタブ オーダーの変更
タブ オーダーでは、TAB キーに移動する入力フォーカス 1 つのコントロールから、[次へ] ダイアログ ボックス内で順序です。 通常、タブ オーダーは、左右から、上からダイアログ ボックスの下部に続行されます。 各コントロールには、 **Tabstop**コントロールが入力フォーカスを受け取るかどうかを決定するプロパティです。  
  
### <a name="to-set-input-focus-for-a-control"></a>コントロールの入力フォーカスを設定するには  
  
1.  [プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)[ **True**または**False**で、 **Tabstop**プロパティです。  
  
 タブ オーダーの一部である場合は True。 の必要性に設定された Tabstop プロパティがないも制御します。 これがあります。 たとえば、する[アクセス キー (ニーモニック) を定義](../windows/defining-mnemonics-access-keys.md)のキャプションがないコントロール。 関連コントロールのアクセス キーが格納される静的テキスト、タブ オーダーの関連するコントロールの直前をする必要があります。  
  
> [!NOTE]
>  ダイアログ ボックスに重複したコントロールが含まれている場合、タブ オーダーを変更すると、コントロールの表示方法は変更できます。 タブ オーダーの後で用意されているコントロールは常に、タブ オーダーでその前にある重複したコントロールの上に表示されます。  
  
#### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスですべてのコントロールの現在のタブ オーダーを表示するには  
  
1.  **形式** メニューのをクリックして**タブ オーダー**です。  
  
 \- または -  
  
-   Ctrl キーを押しながら D.  
  
#### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスのすべてのコントロールのタブ オーダーを変更するには  
  
1.  **形式** メニューのをクリックして**タブ オーダー**です。  
  
     各コントロールの左上隅にある番号は、現在のタブ オーダー内の位置を示します。  
  
2.  タブ オーダーを設定するには、次に TAB キーを目的の順序で各コントロールをクリックします。  
  
3.  キーを押して**ENTER**を終了する**タブ オーダー**モード。  
  
    > [!TIP]
    >  タブ オーダーのモードを入力すると、タブ オーダーを変更する機能を無効にするには、esc キーまたは ENTER キーを押すことができます。  
  
#### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>2 つまたは複数のコントロールのタブ オーダーを変更するには  
  
1.  **形式**] メニューの [選択**タブ オーダー**です。  
  
2.  順序の変更を開始する場所を指定します。 これを行うには、押した、 **CTRL**キーし、1 つの変更後の順序で開始する前にコントロールをクリックします。  
  
     たとえば、7 ~ 9 のコントロールの順序を変更する場合は、ctrl キーを押しながら、し、コントロール 6 を最初に選択します。  
  
    > [!NOTE]
    >  特定のコントロールを (最初に、タブ オーダー) 番号 1 に設定するには、コントロールをダブルクリックします。  
  
3.  CTRL キーを離すと、その時点から次に TAB キーを目的の順序でコントロールをクリックします。  
  
4.  キーを押して**ENTER**を終了する**タブ オーダー**モード。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

