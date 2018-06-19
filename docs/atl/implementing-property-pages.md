---
title: プロパティ ページを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1db6ca4ea374cd76d5b0e1df8e6c0cd03474fdf2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357494"
---
# <a name="implementing-property-pages"></a>プロパティ ページを実装します。
プロパティ ページは、COM オブジェクトを実装する、`IPropertyPage`または**IPropertyPage2**インターフェイスです。 ATL によって、プロパティ ページを実装するためのサポートの提供、 [ATL プロパティ ページ ウィザード](../atl/reference/atl-property-page-wizard.md)で、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)です。  
  
 ATL を使用し、プロパティ ページを作成します。  
  
-   作成または ATL のダイナミック リンク ライブラリ (DLL) のサーバー プロジェクトを開きます。  
  
-   開く、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)選択**ATL プロパティ ページ**です。  
  
-   プロパティ ページがアパートメント スレッドがあるため、ユーザー インターフェイス) を確認します。  
  
-   タイトル、説明 (ドキュメント文字列)、およびページと関連するヘルプ ファイルを設定します。  
  
-   生成されたダイアログ リソース プロパティ ページのユーザー インターフェイスとして機能するには、コントロールを追加します。  
  
-   検証の実行、サイトのページを更新またはページに関連付けられているオブジェクトを更新するページのユーザー インターフェイスの変更に応答します。 具体的には、呼び出す[IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty)ときにユーザーがそのプロパティ ページに変更を加えます。  
  
-   必要に応じてオーバーライドして、`IPropertyPageImpl`以下のガイドラインを使用する方法です。  
  
    |IPropertyPageImpl メソッド|オーバーライドする場合にしています.|メモ|  
    |------------------------------|----------------------------------|-----------|  
    |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|ページおよびサポートするインターフェイスに渡されたオブジェクトの数で基本的な正常性チェックを実行します。|基底クラスの実装を呼び出す前に、独自のコードを実行します。 設定されているオブジェクトが、期待どおりに適合していない場合は、呼び出しをできるだけ早く失敗する必要があります。|  
    |[アクティブ化します。](../atl/reference/ipropertypageimpl-class.md#activate)|ページのユーザー インターフェイス (たとえば、オブジェクトからダイアログ コントロールの現在のプロパティ値の設定、コントロールを動的に作成または他の初期化を実行します) を初期化します。|基本クラスがあるそれらを更新しようとする前に、ダイアログ ウィンドウとすべてのコントロールを作成する機会を持つように、コードの前に、基本クラスの実装を呼び出します。|  
    |[適用](../atl/reference/ipropertypageimpl-class.md#apply)|プロパティの設定を検証し、オブジェクトを更新します。|何もしないトレースとは別の呼び出し後、基本クラスの実装を呼び出す必要はありません。|  
    |[非アクティブ化します。](../atl/reference/ipropertypageimpl-class.md#deactivate)|ウィンドウの関連項目をクリーンアップします。|基本クラスの実装では、プロパティ ページを表す ダイアログ ボックスを破棄します。 ダイアログ ボックスが破棄される前に、クリーンアップする必要がある場合は、基本クラスを呼び出す前に、コードを追加する必要があります。|  
  
 プロパティ ページの実装例を次を参照してください。[例: プロパティ ページを実装する](../atl/example-implementing-a-property-page.md)です。  
  
> [!NOTE]
>  プロパティ ページで ActiveX コントロールをホストにする場合は、ウィザードで生成されたクラスの派生を変更する必要があります。 置き換える**CDialogImpl\<CYourClass >** で**CAxDialogImpl\<CYourClass >** 基底クラスの一覧にします。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [例](../visual-cpp-samples.md)

