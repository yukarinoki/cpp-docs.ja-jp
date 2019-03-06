---
title: '方法: COM コンポーネントを使用する分離アプリケーションをビルドします。'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 01b5c7056bd10a7c1f88df74b5c6b4aa78ff3fde
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417880"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>方法: COM コンポーネントを使用する分離アプリケーションをビルドします。

分離アプリケーションは、プログラムに組み込まれているマニフェストのあるアプリケーションです。 COM コンポーネントを使用する分離アプリケーションを作成することができます。

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>分離アプリケーションのマニフェストを COM 参照を追加するには

1. 分離アプリケーションのプロジェクト プロパティ ページを開きます。

1. 展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。

1. 選択、**分離された COM**プロパティ ページ、および設定して、**コンポーネント ファイル名**プロパティを使用する分離アプリケーションを COM コンポーネントの名前にします。

1. **[OK]** をクリックします。

### <a name="to-build-manifests-into-isolated-applications"></a>分離アプリケーション マニフェストを作成するには

1. 分離アプリケーションのプロジェクト プロパティ ページを開きます。

1. 展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。

1. 選択、**入力し、出力**プロパティ ページ、および設定して、**埋め込みマニフェスト**プロパティを等しく**はい**します。

1. **[OK]** をクリックします。

1. ソリューションをビルドします。

## <a name="see-also"></a>関連項目

[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)<br/>
[サイド バイ サイド アセンブリの概要](/windows/desktop/SbsCs/about-side-by-side-assemblies-)
