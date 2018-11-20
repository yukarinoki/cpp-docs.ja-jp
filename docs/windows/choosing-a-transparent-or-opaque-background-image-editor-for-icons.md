---
title: 透明または不透明な背景の選択 (アイコン用イメージ エディター)
ms.date: 11/19/2018
helpviewer_keywords:
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
ms.openlocfilehash: ceea31b998d5c4dca52657db570ace664f7e373f
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175432"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>透明または不透明な背景の選択 (アイコン用イメージ エディター)

移動またはイメージから選択範囲をコピーするときに現在の背景色に一致するような選択範囲のピクセルは、既定で、透過的です。ターゲットの場所にピクセルが見えにくくならない操作を行います。

透明な背景 (既定値) から、不透明な背景に切り替えるし、再びことができます。 選択ツールを使用するときに、**透明な背景**と**不透明な背景**オプションに表示されます、**オプション**セレクター、**イメージ エディター**ツールバー (以下に示す)。

![オプションをバック グラウンド&#45;非透過または透過](../windows/media/vcimageeditoropaqtranspback.gif "オプションをバック グラウンド&#45;非透過または透過")<br/>
**透過的かつ非透過オプション**上、**イメージ エディターのツールバー**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>透過的なと不透明な背景を切り替える

1. **イメージ エディター**ツールバーで、をクリックして、**オプション**セレクターで、適切な背景を順にクリックします。

   - `Opaque Background (O)`: 既存のイメージは、選択範囲のすべての部分によって隠されています。

   - `Transparent Background (T)`: 既存のイメージは、選択範囲の現在の背景色に一致する部分を示します。

   \- または -

1. **イメージ** を選択またはクリア**描画の不透明な**します。

選択範囲が既にイメージのどの部分は透明を変更する有効なときに、背景色を変更できます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[カラーを使用します。](../windows/working-with-color-image-editor-for-icons.md)