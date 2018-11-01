---
title: イメージのプロパティの変更 (アイコン用イメージ エディター)
ms.date: 11/04/2016
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
ms.openlocfilehash: dae1570ab447a3801e0835ede4502a0626283656
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459947"
---
# <a name="changing-image-properties-image-editor-for-icons"></a>イメージのプロパティの変更 (アイコン用イメージ エディター)

設定またはを使用して、イメージのプロパティを変更することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

### <a name="to-change-an-images-properties"></a>イメージのプロパティを変更するには

1. 内のイメージを開く、**イメージ**エディター。

2. **プロパティ**ウィンドウで、イメージのいずれかまたはすべてのプロパティを変更します。

   |プロパティ|説明|
   |--------------|-----------------|
   |**色**|イメージのカラー スキームを指定します。 選択**モノクロ**、 **16**、または**256**、または**True Color**します。 既に 16 色パレットを使用してイメージを描画した場合は、選択**モノクロ**イメージで色を黒と白の置換が発生します。 コントラストは常に維持されません。 変換など、赤、緑の隣接する領域は両方を黒にします。|
   |**ファイル名**|イメージ ファイルの名前を指定します。 既定では、Visual Studio には、既定のリソース識別子 (IDB_BITMAP1) して、適切な拡張機能を追加すること ("IDB_") の最初の 4 つの文字を削除して作成された基本ファイル名が割り当てられます。 この例では、イメージのファイル名になります`BITMAP1.bmp`します。 その名前を変更することが`MYBITMAP1.bmp`します。|
   |**Height**|イメージの高さをピクセル単位で設定します。 既定値には 48 です。 イメージをトリミングまたは既存のイメージの下の空白領域に追加します。|
   |**ID**|リソースの識別子を設定します。 イメージの Microsoft Visual Studio では、既定で、[次へ] 使用可能な識別子を割り当てます一連: IDB_BITMAP1、IDB_BITMAP2 など。 類似した名前は、アイコンとカーソルに使用されます。|
   |**パレット**|色のプロパティを変更します。 色を選択して表示 をダブルクリック、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)します。 RGB または HSL 値を適切なテキスト ボックスに入力して、色を定義します。|
   |**SaveCompressed**|イメージが圧縮された形式かどうかを示します。 このプロパティは読み取り専用です。 Visual Studio は圧縮された形式で画像を保存することを許可しないため、Visual Studio で作成された任意のイメージのこのプロパティになります**False**します。 このプロパティになります (他のプログラムで作成された) 圧縮されたイメージを開くには、Visual Studio で場合、 **True**します。 Visual Studio を使用して、圧縮されたイメージを保存する場合に圧縮されずにこのプロパティは元に戻す**False**します。|
   |**Width**|イメージの幅をピクセル単位で設定します。 ビットマップの既定値には 48 です。 イメージをトリミングまたは既存のイメージの右側に空白領域を追加します。|

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)