---
title: DCOMCNFG |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DCOMCNFG
dev_langs:
- C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a165102294f9f39d25f0c3118251382ecab067b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357246"
---
# <a name="dcomcnfg"></a>DCOMCNFG
**DCOMCNFG** Windows NT 4.0 ユーティリティで、レジストリで DCOM に固有のさまざまな設定を構成することができます。 **DCOMCNFG**ウィンドウが 3 つのページ: 既定のセキュリティ、既定のプロパティ、およびアプリケーションです。 Windows 2000 では、4 番目のページであり、既定のプロトコルが存在します。  
  
## <a name="default-security-page"></a>既定のセキュリティ ページ  
 既定のセキュリティ ページを使用すると、システムのオブジェクトの既定のアクセス許可を指定します。 既定のセキュリティ ページが 3 つのセクション: アクセス、起動、および構成します。 セクションの既定値を変更するには対応する をクリックします**既定値の編集**ボタンをクリックします。 これらの既定のセキュリティ設定は、下のレジストリに格納されている`HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`です。  
  
## <a name="default-protocols-page"></a>既定のプロトコル ページ  
 このページには、このコンピューターで DCOM を使用可能なネットワーク プロトコルのセットが一覧表示されます。 順序を反映するが使用されます。 優先順位一覧の最初では、最高の優先順位があります。 プロトコルを追加またはこのページから削除できます。  
  
## <a name="default-properties-page"></a>既定のプロパティ ページ  
 [既定のプロパティ] ページで選択する必要があります、**このコンピューターで分散 COM を有効にする**チェック ボックスをこのコンピューターで実行されているオブジェクトを COM へのアクセスを他のコンピューター上のクライアントの場合。 このオプションは設定を選択すると、`HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM`値を`Y`です。  
  
## <a name="applications-page"></a>アプリケーション ページ  
 アプリケーションのページで、特定のオブジェクトの設定を変更するとします。 単に一覧からアプリケーションを選択し、をクリックして、**プロパティ**ボタンをクリックします。 [プロパティ] ウィンドウには、5 つのページがあります。  
  
-   [全般] ページでは、使用しているアプリケーションを確認します。  
  
-   場所 ページでは、クライアントを呼び出すと、アプリケーションの実行場所を指定できます。`CoCreateInstance`関連の CLSID にします。 選択した場合、**次のコンピューターでアプリケーションを実行**チェック ボックスをオンし、コンピューター名を入力し、`RemoteServerName`値がそのアプリケーションの AppID の下に追加します。 オフにすると、**このコンピューターでアプリケーションを実行** チェック ボックスの名前変更、`LocalService`値を`_LocalService`し、それによって、それを無効にします。  
  
-   [セキュリティ] ページがページに記載の既定のセキュリティと同様、 **DCOMCNFG**ウィンドウで、これらの設定は、現在のアプリケーションにのみ適用する点を除いて。 もう一度、設定は、そのオブジェクトの AppID は格納されます。  
  
-   識別 ページでは、アプリケーションを実行するどのユーザーが使用されるを識別します。  
  
-   [エンドポイント] ページには、プロトコルとの DCOM サーバーを選択したクライアントで使用可能なエンドポイントのセットが一覧表示します。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)

