---
title: COM + 1.0、ATL COM + 1.0 コンポーネント ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a23f148fbdc611c8a11d8116b2e7dff34fc9d8f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0、ATL COM+ 1.0 コンポーネント ウィザード
ATL COM + 1.0 コンポーネント ウィザードのこのページを使用すると、サポートするには、インターフェイスの種類と追加のインターフェイスを指定できます。  
  
 ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)です。  
  
 **Interface**  
 オブジェクトがサポートするインターフェイスの種類を示します。 既定では、オブジェクトは、デュアル インターフェイスをサポートします。  
  
|オプション|説明|  
|------------|-----------------|  
|**デュアル**|オブジェクトが、デュアル インターフェイスをサポートするように指定します (その vtable がカスタム インターフェイス関数と遅延バインディング`IDispatch`メソッド)。 COM クライアントとオートメーション コント ローラーの両方が、オブジェクトへのアクセスを許可します。|  
|**カスタム**|オブジェクトが、カスタム インターフェイス (その vtable がカスタム インターフェイス関数) をサポートするように指定します。 カスタム インターフェイスは特にプロセス境界を越えて、デュアル インターフェイスよりも速くなります。<br /><br /> -   **オートメーション互換**カスタム インターフェイスにオートメーションのサポートを追加します。 属性付きプロジェクトは、設定、 **oleautomation**コクラスの属性です。|  
  
 **Queueable**  
 クライアントが非同期的にメッセージ キューを使用して、このコンポーネントを呼び出すことを示します。 .H ファイル (属性付きプロジェクトの場合) または .idl ファイル (プロジェクト属性なし) には、属性付きコンポーネント マクロ カスタム (TLBATTR_QUEUEABLE、0) を追加します。  
  
 **サポート**  
 エラー処理とオブジェクトのコントロールの追加サポートを示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ISupportErrorInfo**|サポートを作成、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|  
|**IObjectControl**|3 つに、オブジェクト アクセスを提供[IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474)メソッド: [Activate](http://msdn.microsoft.com/library/windows/desktop/ms681303)、 [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322)と[非アクティブ化](http://msdn.microsoft.com/library/windows/desktop/ms687094)です。|  
|**IObjectConstruct**|サポートを作成、 [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583)他のメソッドやオブジェクトからパラメーターの受け渡しを管理するインターフェイスです。|  
  
 **トランザクション**  
 オブジェクトがトランザクションをサポートしていることを示します。 .Idl ファイル (プロジェクト属性なし) では、ファイル mtxattr.h が含まれています。  
  
|オプション|説明|  
|------------|-----------------|  
|**サポート状況**|オブジェクトではないことをトランザクション ストリームのルート コンポーネントの属性マクロ custom(TLBATTR_TRANS_SUPPORTED,0) .h ファイル (属性付きプロジェクト)、または .idl ファイル (属性なしプロジェクト) を追加することでを指定します。|  
|**必須**|オブジェクトが場合がありますか、.h ファイル (属性付きプロジェクトの場合) または .idl ファイル (プロジェクト属性なし) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQUIRED,0) を追加することによってトランザクション ストリームのルートができない可能性がありますを指定します。|  
|**サポートされていません**|オブジェクトがトランザクションを除外することを指定します。 .H ファイル (属性付きプロジェクトの場合) または .idl ファイル (プロジェクト属性なし) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_NOTSUPP,0) を追加します。|  
|**新しいが必要です。**|オブジェクトが常にあるトランザクション ストリームのルート コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQNEW,0) .h ファイル (属性付きプロジェクト)、または .idl ファイル (属性なしプロジェクト) を追加することでを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [ATL COM + 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM + 1.0 コンポーネント](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

