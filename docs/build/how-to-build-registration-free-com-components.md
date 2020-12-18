---
description: '詳細情報: 方法:登録を必要としない COM コンポーネントをビルドする'
title: '方法: 登録を必要としない COM コンポーネントをビルドする'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: ddcb378989878749d170705b4808d8302523a73a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162717"
---
# <a name="how-to-build-registration-free-com-components"></a>方法: 登録を必要としない COM コンポーネントをビルドする

登録を必要としない COM コンポーネントは、マニフェストが DLL に組み込まれている COM コンポーネントです。

### <a name="to-build-manifests-into-com-components"></a>COM コンポーネントにマニフェストを組み込むには

1. COM コンポーネントのプロジェクト プロパティ ページを開きます。

1. **[構成プロパティ]** ノードを展開し、 **[マニフェスト ツール]** ノードを展開します。

1. **[入出力]** プロパティ ページを選択し、 **[埋め込みマニフェスト]** プロパティを **[はい]** に設定します。

1. **[OK]** をクリックします。

1. ソリューションをビルドします。

## <a name="see-also"></a>関連項目

[方法: COM コンポーネントを使用する分離アプリケーションをビルドする](how-to-build-isolated-applications-to-consume-com-components.md)
