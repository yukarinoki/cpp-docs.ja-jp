---
title: ガイドのコントロールの配置
ms.date: 11/04/2016
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
ms.openlocfilehash: 182cae288f4882611ec3d535357b93bf6d6ea9c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491092"
---
# <a name="aligning-controls-on-a-guide"></a>ガイドのコントロールの配置

コントロールのサイズ変更ハンドルは、コントロールを移動するととガイドがコントロールにスナップする (ガイドに合わせてコントロールが存在しない) 場合、に、ガイドにスナップされます。 ガイドが移動したときにスナップしたコントロールも移動します。 ガイドでは、いずれかが移動すると、コントロールの 1 つ以上のガイドを基準としてスナップされますがサイズ変更されます。

ガイドとコントロールの間隔を決定する定規の目盛りは、ダイアログ単位 (Dlu) によって定義されます。 DLU は、通常、8 ポイント MS Shell Dlg、ダイアログ ボックス フォントのサイズに基づきます。 水平 DLU は、4、ダイアログ ボックスのフォントの平均幅です。 垂直 DLU は 8 で割った値のフォントの高さの平均値です。

### <a name="to-size-a-group-of-controls-with-guides"></a>ガイドを使用してコントロールのグループのサイズ

1. コントロール (またはコントロール) の一方の側をスナップをガイドします。

2. コントロール (またはコントロール) の反対側のガイドをドラッグします。

   複数のコントロールで必要に応じて、それぞれに 2 番目のガイドへのスナップのサイズします。

3. コントロール (またはコントロール) のサイズのいずれかのガイドに移動します。

### <a name="to-change-the-intervals-of-the-tick-marks"></a>目盛りの間隔を変更するには

1. **形式** メニューの 選択**ガイド設定**です。

2. [ガイドの設定 ダイアログ ボックス](../windows/guide-settings-dialog-box.md)の**グリッド間隔**フィールドに、Dlu の新しい幅と高さを指定します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ エディターの状態 (ガイドとグリッド)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)