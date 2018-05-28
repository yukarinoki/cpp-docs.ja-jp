---
title: コンボ ボックス コントロールに値を追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [Visual Studio], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- controls [C++], testing values in combo boxes
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c81e40de56970571ad78ceea86084b7ff7b82227
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="adding-values-to-a-combo-box-control"></a>コンボ ボックス コントロールへの値の追加
ダイアログ エディターを開く必要がある限り、コンボ ボックス コントロールに値を追加できます。  
  
> [!TIP]
>  コンボ ボックスにすべての値を追加することをお勧め*する前に*ダイアログ エディターで、ボックスのサイズを変更またはコンボ コントロールに表示されるテキストを切り捨てることがあります。  
  
#### <a name="to-enter-values-into-a-combo-box-control"></a>コンボ ボックス コントロールに値を入力するには  
  
1.  クリックして、コンボ ボックス コントロールを選択します。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、下方向にスクロール、**データ**プロパティです。  
  
    > [!NOTE]
    >  種類でグループ化されたプロパティを表示する場合**データ**に表示されます、**その他**プロパティです。  
  
3.  [値] 領域でをクリックして、**データ**セミコロンで区切られたプロパティと、データの値を入力します。  
  
    > [!NOTE]
    >  スペースは、ドロップダウン リストで項目がアルファベット順に干渉するためには、値の間のスペースを入れないでください。  
  
4.  をクリックして**Enter**値の追加が完了したらです。  
  
 コンボ ボックスのドロップダウン部分を拡大する方法については、次を参照してください。[し、コンボ ボックスのドロップダウン リストのサイズの設定](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)です。  
  
> [!NOTE]
>  この手順を使用して Win32 プロジェクトに値を追加することはできません (、**データ**Win32 プロジェクトのプロパティが淡色表示)。 Win32 プロジェクトには、この機能を追加するライブラリはありません、ためプログラムで、Win32 プロジェクトのコンボ ボックスに値を追加する必要があります。  
  
#### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>コンボ ボックスで値の外観をテストするには  
  
1.  内の値を入力した後に、**データ**プロパティ、をクリックして、**テスト**のボタンでは、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)です。  
  
     値全体の一覧を下へスクロールしてみてください。 入力されたとおりに値が表示されます、**データ**プロパティ ウィンドウでプロパティです。 スペルまたは大文字小文字のチェックはありません。  
  
     ダイアログ ボックス エディターに戻るには、esc キーを押します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

