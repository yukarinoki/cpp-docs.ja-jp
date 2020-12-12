---
description: 詳細については、「ATL プロジェクトでの COM + 1.0 のサポート」を参照してください。
title: ATL プロジェクトでの COM + 1.0 のサポート
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 8e196bccf25667da28532248765e47906fdcee97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141285"
---
# <a name="com-10-support-in-atl-projects"></a>ATL プロジェクトでの COM + 1.0 のサポート

[ATL プロジェクトウィザード](../../atl/reference/creating-an-atl-project.md)を使用して、com + 1.0 コンポーネントの基本サポートを含むプロジェクトを作成できます。

COM + 1.0 は、分散コンポーネントベースのアプリケーションを開発するために設計されています。 また、これらのアプリケーションをデプロイおよび管理するためのランタイムインフラストラクチャも提供します。

[ **COM + 1.0 をサポート** する] チェックボックスをオンにすると、ウィザードによって、リンク手順でビルドスクリプトが変更されます。 具体的には、COM + 1.0 プロジェクトは次のライブラリにリンクしています。

- comsvcs .lib

- Mtxguid

[ **COM + 1.0 をサポート** する] チェックボックスをオンにした場合は、[ **サポートコンポーネントレジストラー**] を選択することもできます。 コンポーネントレジストラーを使用すると、COM + 1.0 オブジェクトは、コンポーネントの一覧を取得したり、コンポーネントを登録したり、コンポーネントの登録を解除したりできます (個別またはすべてを一度に行うことができます)。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL および C Run-Time コードを使用したプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)
