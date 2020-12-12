---
description: 詳細については、「ATL Services」を参照してください。
title: ATL サービス
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 1cb1f526434cefe57dc4675d592f836e04a6cdb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148604"
---
# <a name="atl-services"></a>ATL サービス

ATL COM オブジェクトを作成してサービスで実行されるようにするには、ATL プロジェクトウィザードのサーバーオプションの一覧から [Service (EXE)] を選択します。 次に、ウィザードは、から派生したクラスを作成し `CAtlServiceModuleT` てサービスを実装します。

ATL COM オブジェクトがサービスとして構築されると、ローカルサーバーとしてのみ登録され、コントロールパネルの [サービス] の一覧には表示されません。 これは、サービスをサービスとしてのローカルサーバーとしてデバッグする方が簡単であるためです。 サービスとしてインストールするには、コマンドプロンプトで次のコマンドを実行します。

`YourEXE` `.exe /Service`

アンインストールするには、次のように実行します。

`YourEXE` `.exe /UnregServer`

このセクションの最初の4つのトピックでは、メンバー関数の実行中に発生するアクションについて説明し `CAtlServiceModuleT` ます。 これらのトピックは、通常呼び出される関数と同じ順序で表示されます。 これらのトピックの理解を深めるために、ATL プロジェクトウィザードで生成されたソースコードを参照として使用することをお勧めします。 最初の4つのトピックは次のとおりです。

- [CAtlServiceModuleT:: Start 関数](../atl/reference/catlservicemodulet-class.md#start)

- [CAtlServiceModuleT:: ServiceMain 関数](../atl/reference/catlservicemodulet-class.md#servicemain)

- [CAtlServiceModuleT:: Run 関数](../atl/reference/catlservicemodulet-class.md#run)

- [CAtlServiceModuleT:: Handler 関数](../atl/reference/catlservicemodulet-class.md#handler)

最後の3つのトピックでは、サービスの開発に関連する概念について説明します。

- ATL サービスの[レジストリエントリ](../atl/registry-entries.md)

- [DCOMCNFG](../atl/dcomcnfg.md)

- ATL サービスの[デバッグのヒント](../atl/debugging-tips.md)

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
