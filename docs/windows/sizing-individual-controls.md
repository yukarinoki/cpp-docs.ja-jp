---
title: コントロールのサイズ変更
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
ms.openlocfilehash: a6381dcf1aeb9f73ac3b656229d9332df2a6a519
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742714"
---
# <a name="sizing-controls"></a>コントロールのサイズ変更

コントロールのサイズを変更するのにには、サイズ変更ハンドルを使用します。 サイズ変更ハンドルにポインターを置き、ときにコントロールをサイズ変更できる方向を示すために図形を変更します。 アクティブなサイズ変更ハンドルは、solid;サイズ変更ハンドルが中空の場合は、その軸に沿ったコントロールのサイズ変更することはできません。

ガイドまたは余白、コントロールをスナップしてコントロールのサイズを変更することもできます。 または移動することによって 1 つは、制御し、ガイド スナップします。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="to-size-an-individual-control"></a>個々 のコントロールのサイズ

1. コントロールを選択します。

1. コントロールのサイズを変更するサイズ変更ハンドルをドラッグします。

   - サイズ変更ハンドルの上部と辺には、水平または垂直方向のサイズを変更します。

   - 角にあるサイズ変更ハンドルは、水平および垂直の両方向のサイズを変更します。

   > [!TIP]
   > 押しながら、時にコントロールの 1 つのダイアログ単位 (DLU) を変更すること、 **Shift**キーを使用して、 **→**と**↓**キー。

## <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>内のテキストに合わせてコントロールのサイズを自動的にする

選択**コンテンツ サイズ**から、**形式**メニュー。

\- または -

コントロールを右クリックし、選択**コンテンツ サイズ**ショートカット メニューから。

## <a name="to-make-controls-the-same-width-height-or-size"></a>同じ幅、高さ、またはサイズを制御するには

主要なコントロールのサイズに基づいてコントロールのグループのサイズを変更することができます。

1. [コントロールを選択する](../windows/selecting-multiple-controls.md)サイズを変更します。

   シリーズの最初に選択コントロールは、主要なコントロールです。 グループ内のコントロールの最終的なサイズは、主要なコントロールのサイズによって異なります。 主要なコントロールを選択する方法の詳細については、次を参照してください。[主要なコントロールを指定する](../windows/specifying-the-dominant-control.md)します。

1. **形式**] メニューの [選択**同じサイズに揃える**、次のコマンドのいずれかを選択します。

   - **両方とも**

   - **Height**

   - **Width**

## <a name="to-set-the-size-of-the-combo-box-and-its-drop-down-list"></a>ボックスとドロップダウン リストに、コンボ ボックスのサイズを設定するには

ダイアログ ボックスを追加すると、コンボ ボックスを調整することができます。 ドロップダウン リスト ボックスのサイズを指定することもできます。 詳細については、次を参照してください。[値コンボ ボックス コントロールを追加](../windows/adding-values-to-a-combo-box-control.md)します。

### <a name="to-size-a-combo-box"></a>コンボ ボックスのサイズ

1. ダイアログ ボックスで、コンボ ボックス コントロールを選択します。

   最初に、左右のサイズ変更ハンドルのみがアクティブです。

1. コンボ ボックスの幅を設定するのにには、サイズ変更ハンドルを使用します。

コンボ ボックスのドロップダウン部分の縦のサイズを設定することもできます。

### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>コンボ ボックスのサイズのボックスのドロップダウン リストを設定するには

1. コンボ ボックスの右側にある下矢印ボタンを選択します。

   ![MFC プロジェクト コンボ ボックスの矢印](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   拡張領域のドロップダウンの一覧をコンボ ボックスのサイズを表示するコントロールの変更の概略です。

1. 下のサイズ変更ハンドルを使用すると、ドロップダウン リストの領域の初期サイズを変更できます。

   ![コンボ&#45;MFC プロジェクトで、ボックスのサイズ変更](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. コンボ ボックスのドロップダウン リストの部分を終了するには、もう一度ドロップダウン矢印を選択します。

## <a name="to-set-the-width-of-a-horizontal-scroll-bar-and-make-it-appear"></a>水平スクロール バーの幅を設定し、表示されるようにするには

MFC クラスを使用してダイアログ ボックスに水平スクロール バーを使用して、リスト ボックスを追加すると、スクロール バーは、アプリケーションに自動的に表示されません。

最も幅の広い要素の最大の幅を呼び出すことによって設定[CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent)コードにします。

   この値を設定せず、スクロール バーは表示されません、でも、リスト ボックス内の項目は、ボックスよりも広い場合。
> [!NOTE]
> 水平スクロール バーには、MFC が必要です。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)
