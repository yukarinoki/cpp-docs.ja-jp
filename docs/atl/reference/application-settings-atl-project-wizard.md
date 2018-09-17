---
title: アプリケーションの設定、ATL プロジェクト ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49e25fa8a730ea31caf747d07ce30a0622c4bd01
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714689"
---
# <a name="application-settings-atl-project-wizard"></a>[アプリケーションの設定] (ATL プロジェクト ウィザード)

使用して、**アプリケーション設定**デザインし、基本的な機能を新しい ATL プロジェクトに追加する ATL プロジェクト ウィザードのページ。

## <a name="server-type"></a>サーバーの種類

次の 3 つのサーバーの種類のいずれかから選択します。

- **ダイナミック リンク ライブラリ (DLL)**  

   プロセスでサーバーを作成する場合に選択します。

- **実行可能ファイル (EXE)**  

   選択すると、ローカルのアウト プロセス サーバーを作成します。 このオプションでは、MFC または COM + 1.0 のサポートは許可されません。 プロキシ/スタブ コードのマージのことはできません。

- **サービス (EXE)**  

   Windows の起動時に、バック グラウンドで実行されている Windows アプリケーションを作成する場合に選択します。 このオプションは、MFC または COM + 1.0 のサポートを許可しないか、プロキシ/スタブ コードのマージは許可されません。

## <a name="additional-options"></a>追加オプション

> [!NOTE]
> その他のオプションは、DLL プロジェクトにのみ使用できます。

- **プロキシ/スタブ コードのマージを許可します。**  

   選択、**プロキシ/スタブ コードをマージ**インターフェイスのマーシャ リングすることが必要な場合は便利なようにチェック ボックスをオンします。 このオプションは、同じ、MIDL で生成されたプロキシとスタブ コードを実行可能ファイル サーバーとして。

- **MFC のサポート**  

   オブジェクトが、MFC のサポートが含まれることを選択します。 このオプションは、クラスとが含まれている関数のいずれかをアクセスできるように、MFC ライブラリにプロジェクトをリンクします。

- **COM + 1.0 のサポート**  

   COM + 1.0 コンポーネントをサポートするプロジェクトのビルド設定を変更する場合に選択します。 ライブラリの標準の一覧だけでなく、ウィザードは、COM + 1.0 コンポーネント固有のライブラリ comsvcs.lib を追加します

   さらに、mtxex.dll は、アプリケーションを起動するときに、ホスト システムに読み込まれる遅延です。

- **コンポーネント レジストラーのサポート**

   ATL プロジェクトに COM + 1.0 コンポーネントのサポートが含まれている場合は、このオプションを設定することができます。 コンポーネント レジストラーは、COM + 1.0 オブジェクトをコンポーネントの一覧を取得、コンポーネントを登録または (個別にまたは一括) コンポーネントの登録を解除できます。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

