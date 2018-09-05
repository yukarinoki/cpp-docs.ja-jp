---
title: COM + 1.0 ATL プロジェクトのサポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a9e6cd4a374f0941b360a3f8f24f61e4b46a6a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763299"
---
# <a name="com-10-support-in-atl-projects"></a>COM + 1.0 ATL プロジェクトでサポートします。

使用することができます、 [ATL プロジェクト ウィザード](../../atl/reference/creating-an-atl-project.md)COM + 1.0 コンポーネントの基本的なサポートでプロジェクトを作成します。

COM + 1.0 は、コンポーネント ベースの分散アプリケーションを開発するために設計されています。 展開すると、これらのアプリケーションを管理するランタイムのインフラストラクチャも提供します。

選択した場合、 **COM + 1.0 のサポート**チェック ボックス、ウィザードは、リンクの手順で、ビルド スクリプトを変更します。 具体的には、COM + 1.0 プロジェクトへのリンク、次のライブラリ:

- comsvcs.lib

- Mtxguid.lib

選択した場合、 **COM + 1.0 のサポート**チェック ボックスを選択することも**サポート コンポーネント レジストラー**します。 コンポーネント レジストラーは、COM + 1.0 オブジェクトをコンポーネントの一覧を取得、コンポーネントを登録または (個別にまたは一括) コンポーネントの登録を解除できます。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)   
[ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

