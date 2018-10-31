---
title: プロパティ ページの実装 |Microsoft Docs
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
ms.openlocfilehash: f00e95aee0f3e16a979f4969a33b90746b4082ea
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062406"
---
# <a name="implementing-property-pages"></a>プロパティ ページの実装

プロパティ ページは、COM オブジェクトを実装する、`IPropertyPage`または`IPropertyPage2`インターフェイス。 ATL によって、プロパティ ページを実装するためのサポートの提供、 [ATL プロパティ ページ ウィザード](../atl/reference/atl-property-page-wizard.md)で、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)します。

ATL を使用してプロパティ ページを作成します。

- 作成または ATL のダイナミック リンク ライブラリ (DLL) のサーバー プロジェクトを開きます。

- 開く、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)選択**ATL プロパティ ページ**します。

- プロパティ ページがアパートメント スレッドがあるため、ユーザー インターフェイス) を確認します。

- タイトル、説明 (ドキュメント文字列)、およびページに関連するヘルプ ファイルを設定します。

- 生成されたダイアログ リソース プロパティ ページのユーザー インターフェイスとして機能するには、コントロールを追加します。

- 検証を実行、ページのサイトを更新、または、ページに関連付けられたオブジェクトを更新するページのユーザー インターフェイスの変更に応答します。 具体的には、呼び出す[IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty)ユーザーがプロパティ ページに変更を行ったとします。

- 必要に応じてオーバーライドして、`IPropertyPageImpl`メソッドを次のガイドラインを使用します。

   |IPropertyPageImpl メソッド|オーバーライドする場合に.|メモ|
   |------------------------------|----------------------------------|-----------|
   |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|ページおよびサポートするインターフェイスに渡されたオブジェクトの数に基本的なサニティ チェックを実行します。|基本クラスの実装を呼び出す前に、独自のコードを実行します。 設定されているオブジェクトが、期待どおりに準拠していない場合は、呼び出しをできるだけ早く失敗する必要があります。|
   |[アクティブ化します。](../atl/reference/ipropertypageimpl-class.md#activate)|ページのユーザー インターフェイス (たとえば、オブジェクトから現在のプロパティ値を持つダイアログ コントロールを設定、コントロールを動的に作成またはその他の初期化を実行します) を初期化します。|基底クラスがあるそれらを更新する前に、ダイアログ ウィンドウおよびすべてのコントロールを作成することになるように、コードの前に、基本クラスの実装を呼び出します。|
   |[適用します。](../atl/reference/ipropertypageimpl-class.md#apply)|プロパティの設定を検証し、オブジェクトを更新します。|これは何もトレースとは別の呼び出しから基本クラスの実装を呼び出す必要はありません。|
   |[非アクティブ化します。](../atl/reference/ipropertypageimpl-class.md#deactivate)|ウィンドウの関連項目をクリーンアップします。|基本クラスの実装では、プロパティ ページを表す ダイアログ ボックスを破棄します。 ダイアログ ボックスが破棄される前に、クリーンアップする必要がある場合は、基本クラスを呼び出す前に、コードを追加する必要があります。|

例プロパティ ページの実装を参照してください。[例: プロパティ ページを実装する](../atl/example-implementing-a-property-page.md)します。

> [!NOTE]
> プロパティ ページに ActiveX コントロールをホストする場合は、ウィザードで生成されたクラスの派生を変更する必要があります。 置換**CDialogImpl\<CYourClass >** で**CAxDialogImpl\<CYourClass >** 基底クラスの一覧にします。

## <a name="see-also"></a>関連項目

[プロパティ ページ](../atl/atl-com-property-pages.md)<br/>
[例](../visual-cpp-samples.md)
