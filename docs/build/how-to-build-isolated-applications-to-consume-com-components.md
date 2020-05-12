---
title: '方法: COM コンポーネントを使用する分離アプリケーションをビルドする'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 8ae3c51502267f202cbb85ea7be2a81dc3310410
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493235"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>方法: COM コンポーネントを使用する分離アプリケーションをビルドする

分離アプリケーションは、マニフェストがプログラムに組み込まれているアプリケーションです。 COM コンポーネントを使用する分離アプリケーションを作成できます。

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>分離アプリケーションのマニフェストに COM 参照を追加するには

1. 分離アプリケーションのプロジェクト プロパティ ページを開きます。

1. **[構成プロパティ]** ノードを展開し、 **[マニフェスト ツール]** ノードを展開します。

1. **[分離 COM]** プロパティ ページを選択し、 **[コンポーネント ファイル名]** プロパティを、分離アプリケーションに使用させる COM コンポーネントの名前に設定します。

1. **[OK]** をクリックします。

### <a name="to-build-manifests-into-isolated-applications"></a>分離アプリケーションにマニフェストを組み込むには

1. 分離アプリケーションのプロジェクト プロパティ ページを開きます。

1. **[構成プロパティ]** ノードを展開し、 **[マニフェスト ツール]** ノードを展開します。

1. **[入出力]** プロパティ ページを選択し、 **[埋め込みマニフェスト]** プロパティを **[はい]** に設定します。

1. **[OK]** をクリックします。

1. ソリューションをビルドします。

## <a name="see-also"></a>関連項目

[分離アプリケーション](/windows/win32/SbsCs/isolated-applications)<br/>
[side-by-side アセンブリについて](/windows/win32/SbsCs/about-side-by-side-assemblies-)
