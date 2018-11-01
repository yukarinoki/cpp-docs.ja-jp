---
title: イメージのサイズ変更 (アイコン用イメージ エディター)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
ms.openlocfilehash: 721a8f1de511c105df5d72bbe60685d210ad5a94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576099"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>イメージのサイズ変更 (アイコン用イメージ エディター)

動作、**イメージ**イメージのサイズ変更中にエディターがしたかどうかに依存[選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)イメージ全体または一部だけです。

選択範囲には、イメージの一部のみが含まれている場合、**イメージ**エディターは、現在の背景色で領域をピクセルの行または列を削除して選択範囲を縮小またはで選択範囲を拡大ピクセルの行または列を複製します。

選択範囲には、全体のイメージが含まれている場合、**イメージ**エディターか、圧縮、イメージを拡大またはトリミングおよび拡張されています。

イメージのサイズ変更の 2 つのメカニズムがある: サイズ変更ハンドルと[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 イメージの一部またはすべてのサイズを変更するサイズ変更ハンドルをドラッグすることができます。 サイズ変更ハンドルをドラッグすることは、solid です。 白抜きのハンドルをドラッグすることはできません。 使用することができます、**プロパティ**全体のサイズを変更するにはウィンドウのイメージのみ、選択したパーツではありません。

![サイズ変更ハンドルをビットマップに](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")<br/>
サイズ変更ハンドル

> [!NOTE]
> ある場合、**タイル グリッド**で選択したオプション、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)、[次へ] のタイル グリッド線にスナップのサイズを変更します。 だけの場合、**ピクセル グリッド**オプションは、(既定の設定) を選択するには、次のピクセルにスナップのサイズを変更します。

- [イメージ全体のサイズ変更](../windows/resizing-an-entire-image-image-editor-for-icons.md)

- [全体のイメージ トリミングまたは拡張](cropping-or-extending-an-entire-image-image-editor-for-icons.md)

- [全体のイメージ縮小または拡大](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)

- [縮小またはイメージの一部を拡大](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)