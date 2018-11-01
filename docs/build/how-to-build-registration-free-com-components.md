---
title: '方法 : 登録を必要としない COM をビルドする'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 4f4ebf121b761c37969fa3f9788bda52d913f340
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463532"
---
# <a name="how-to-build-registration-free-com-components"></a>方法 : 登録を必要としない COM をビルドする

登録を必要としない COM コンポーネントは、Dll に組み込まれているマニフェストのある COM コンポーネントです。

### <a name="to-build-manifests-into-com-components"></a>COM コンポーネントにマニフェストをビルドするには

1. COM コンポーネントのプロジェクト プロパティ ページを開きます。

1. 展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。

1. 選択、**入力し、出力**プロパティ ページ、および設定して、**埋め込みマニフェスト**プロパティを等しく**はい**します。

1. **[OK]** をクリックします。

1. ソリューションをビルドします。

## <a name="see-also"></a>関連項目

[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)<br/>
[サイド バイ サイド アセンブリの概要](/windows/desktop/SbsCs/about-side-by-side-assemblies-)<br/>
[方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)