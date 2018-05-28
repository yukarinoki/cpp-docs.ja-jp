---
title: イメージのプロパティ (アイコン用イメージ エディター) を変更する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Image editor [C++], image properties
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79903e198ddd418b96b0fac2a464dc130d81614e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="changing-image-properties-image-editor-for-icons"></a>イメージのプロパティの変更 (アイコン用イメージ エディター)
設定またはを使用して、イメージのプロパティを変更することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
### <a name="to-change-an-images-properties"></a>イメージのプロパティを変更するには  
  
1.  内のイメージを開く、**イメージ**エディターです。  
  
2.  **プロパティ** ウィンドウで、イメージの一部またはすべてのプロパティを変更します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |**色**|イメージのカラー スキームを指定します。 モノクロ、16、または 256、または True 色を選択します。 既に 16 色パレットでイメージを描画した場合に、イメージ内の色を黒と白の置換モノクロを選択するとします。 コントラストは常に維持されません。 たとえば、赤と緑の隣接する領域両方黒に変換されます。|  
    |**ファイル名**|イメージ ファイルの名前を指定します。 既定では、Visual Studio には、既定のリソース識別子 (IDB_BITMAP1) と、適切な拡張を追加することから基本ファイル名の最初の 4 文字 ("IDB_") を削除することによって作成されたが割り当てられます。 この例では、イメージのファイル名を BITMAP1.bmp となります。 MYBITMAP1.bmp を変更する可能性があります。|  
    |**Height**|ピクセル単位で、イメージの高さを設定します。 既定値は、48 です。 イメージのトリミングまたは既存のイメージの下の空白を追加します。|  
    |**ID**|リソースの識別子を設定します。 イメージの Microsoft Visual Studio では、既定では、識別子が割り当てられます、[次へ] 使用可能な一連の: IDB_BITMAP1、IDB_BITMAP2、となります。 類似した名前は、アイコンとカーソルに使用されます。|  
    |**パレット**|色のプロパティを変更します。 色を選択し、表示するにはダブルクリック、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)です。 色を定義するには、該当するテキスト ボックスに RGB または HSL 値を入力します。|  
    |**SaveCompressed**|イメージが圧縮形式であるかどうかを示します。 このプロパティは読み取り専用です。 Visual Studio が、圧縮形式で画像を保存を許可していないので、Visual Studio で作成されたイメージはすべて、このプロパティは**False**です。 このプロパティになります (別のプログラムで作成された) 圧縮されたイメージを開くには、Visual Studio で場合、 **True**です。 Visual Studio を使用して圧縮されたイメージを保存する場合は、これは圧縮されずにこのプロパティに戻ります**False**です。|  
    |**Width**|ピクセル単位で、イメージの幅を設定します。 ビットマップの既定値は、48 です。 イメージのトリミングまたは既存のイメージの右側に空白を追加します。|  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

