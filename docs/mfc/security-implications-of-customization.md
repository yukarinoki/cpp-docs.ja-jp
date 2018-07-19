---
title: カスタマイズのセキュリティに対する影響 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1416a586af479ea7b476a6c85d45992ba18873ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379419"
---
# <a name="security-implications-of-customization"></a>カスタマイズによるセキュリティへの影響
このトピックでは、MFC で潜在的なセキュリティの弱点について説明します。  
  
## <a name="potential-security-weakness"></a>潜在的なセキュリティの弱点  
 MFC で、ユーザーは、アプリケーション ユーザー インターフェイス、たとえば、ボタンやアイコンの外観の外観をカスタマイズします。 MFC には、ユーザーがシェル コマンドを実行できるようにユーザー定義のツールもサポートしています。 アプリケーションのカスタマイズした設定がレジストリ内のユーザー プロファイルに保存されるため、セキュリティの脆弱性が発生します。 これらの設定を編集し、アプリケーションの外観または動作を変更、レジストリにアクセスできるユーザーできます。 など、コンピューターの管理者では、ユーザーのアプリケーション (ネットワーク共有) からでも任意のプログラムを実行することで、ユーザーを偽装する可能性があります。  
  
## <a name="workarounds"></a>問題回避  
 レジストリの脆弱性を終了するこれら 3 つの方法のいずれかをお勧めします。  
  
-   格納されているデータを暗号化します。  
  
-   レジストリではなく、セキュリティで保護されたファイルにデータを格納します。  
  
     これらの最初の 2 つの方法のいずれかを行うためには、派生クラスを[CSettingsStore クラス](../mfc/reference/csettingsstore-class.md)暗号化またはレジストリの外部記憶域を実装するメソッドをオーバーライドします。  
  
-   また、アプリケーションでのカスタマイズを無効にすることができます。  
  
## <a name="see-also"></a>関連項目  
 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)

