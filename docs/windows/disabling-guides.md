---
title: ガイドを無効にする |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, disabling snapping
- Dialog editor [C++], snap to guides
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
ms.assetid: 51efa07b-8684-474e-a0b4-191ec5d91d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e3ae2e982ce04743644f9c94d9c163478c0b67e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313118"
---
# <a name="disabling-guides"></a>ガイドの無効化

ガイド、スナップに効果を無効にするのに、マウスと組み合わせて特殊なキーを使用できます。 使用して、 **Alt**キーが選択されているガイドのスナップの効果を無効にします。 ガイドを移動、 **Shift**キーは、スナップしたコントロールが、ガイドに移動しないようにします。

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>ガイド、スナップに効果を無効にするには

1. 押しながら、コントロールをドラッグ、 **Alt**キー。

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>スナップしたコントロールを移動せずにガイドを移動するには

1. 押しながら、ガイドをドラッグ、 **Shift**キー。

### <a name="to-turn-off-the-guides"></a>ガイドでは、オフにするには

1. **形式** メニューの 選択**ガイド設定**です。

2. [ガイドの設定 ダイアログ ボックス](../windows/guide-settings-dialog-box.md)**レイアウト ガイド** **None**です。

   > [!NOTE]
   > アクセスは、ルーラー バーをダブルクリックすることも、**ガイド設定** ダイアログ ボックス。

\- または -

- **形式** メニューのをクリックして**ガイドの切り替え**です。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ エディターの状態 (ガイドとグリッド)](../windows/dialog-editor-states-guides-and-grids.md)  
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)