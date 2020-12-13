---
description: '詳細情報: DCOMCNFG'
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: d99b0018d63cedbccaf57ec4cadeb649f390dcf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153162"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG は、レジストリ内のさまざまな DCOM 固有の設定を構成できる Windows NT 4.0 ユーティリティです。 DCOMCNFG ウィンドウには、既定のセキュリティ、既定のプロパティ、およびアプリケーションという3つのページがあります。 Windows 2000 では、既定のプロトコルである4ページが存在します。

## <a name="default-security-page"></a>[既定のセキュリティ] ページ

[既定のセキュリティ] ページを使用すると、システム上のオブジェクトに対する既定のアクセス許可を指定できます。 [既定のセキュリティ] ページには、[アクセス]、[起動]、[構成] の3つのセクションがあります。 セクションの既定値を変更するには、対応する [ **既定値の編集** ] ボタンをクリックします。 これらの既定のセキュリティ設定は、のレジストリに格納され `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE` ます。

## <a name="default-protocols-page"></a>[既定のプロトコル] ページ

このページには、このコンピューター上の DCOM で使用可能な一連のネットワークプロトコルが一覧表示されます。 順序は、使用される優先度を反映しています。リストの最初のは、最も高い優先順位を持ちます。 このページでは、プロトコルを追加または削除できます。

## <a name="default-properties-page"></a>[既定のプロパティ] ページ

他のコンピューター上のクライアントがこのコンピューターで実行されている COM オブジェクトにアクセスできるようにする場合は、[既定のプロパティ] ページで [ **このコンピューターの分散 COM を有効** にする] チェックボックスをオンにする必要があります。 このオプションを選択すると、値がに設定さ `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` `Y` れます。

## <a name="applications-page"></a>アプリケーション ページ

[アプリケーション] ページでは、特定のオブジェクトの設定を変更します。 一覧からアプリケーションを選択し、[ **プロパティ** ] ボタンをクリックするだけです。 プロパティウィンドウには、次の5つのページがあります。

- [全般] ページで、使用しているアプリケーションを確認します。

- [場所] ページでは、クライアントが関連する CLSID でを呼び出したときにアプリケーションを実行する場所を指定でき `CoCreateInstance` ます。 [ **次のコンピューターでアプリケーションを実行** する] チェックボックスをオンにしてコンピューター名を入力すると、 `RemoteServerName` そのアプリケーションの AppID の下に値が追加されます。 [ **このコンピューターでアプリケーションを実行** する] チェックボックスをオフに `LocalService` すると、値がに変更さ `_LocalService` れ、無効になります。

- [セキュリティ] ページは、[DCOMCNFG] ウィンドウの [既定のセキュリティ] ページに似ていますが、これらの設定は現在のアプリケーションにのみ適用される点が異なります。 この場合も、設定はそのオブジェクトの AppID の下に格納されます。

- [識別] ページでは、アプリケーションの実行に使用するユーザーを識別します。

- [エンドポイント] ページには、選択した DCOM サーバーのクライアントが使用できるプロトコルとエンドポイントのセットが一覧表示されます。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)
