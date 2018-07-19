---
title: プロパティ ページ (ATL) の実装 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4c7329e7784fc5228bca5aa5b167d04ded51aaf
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852285"
---
# <a name="example-implementing-a-property-page"></a>例: プロパティ ページの実装
この例は、プロパティ ページのプロパティを表示します (および変更することができます) を作成する方法を示しています、[ドキュメント クラス](../mfc/document-classes.md)インターフェイス。  
  
 この例がに基づいて、[例](../visual-cpp-samples.md)します。  
  
 この例を完了するには、ことができます。  
  
- [ATL プロパティ ページ クラスを追加](#vcconusing_the_atl_object_wizard)クラスの追加 ダイアログ ボックスと ATL プロパティ ページ ウィザードを使用します。  
  
- [ダイアログ リソースの編集](#vcconediting_the_dialog_resource)の興味深いプロパティ用の新しいコントロールを追加することで、`Document`インターフェイス。  
  
- [メッセージ ハンドラーを追加する](#vcconadding_message_handlers)プロパティ ページのサイトを保持する、ユーザーが行った変更の通知。  
  
-   いくつか追加`#import`ステートメントとの typedef、[ハウスキーピング](#vcconhousekeeping)セクション。  
  
- [オーバーライドのために](#vcconoverriding_ipropertypageimpl_setobjects)プロパティ ページに渡されるオブジェクトを検証します。  
  
- [オーバーライドのために](#vcconoverriding_ipropertypageimpl_activate)プロパティ ページのインターフェイスを初期化します。  
  
- [オーバーライド IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply)を最新のプロパティ値を持つオブジェクトを更新します。  
  
- [プロパティ ページを表示](#vccontesting_the_property_page)簡単なヘルパー オブジェクトを作成します。  
  
- [マクロを作成する](#vcconcreating_a_macro)プロパティ ページをテストするされます。  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> ATL プロパティ ページ クラスの追加  
 まず、という名前の DLL サーバーの新しい ATL プロジェクト作成`ATLPages7`です。 使用して、 [ATL プロパティ ページ ウィザード](../atl/reference/atl-property-page-wizard.md)プロパティ ページを生成します。 プロパティ ページ、**短い名前**の**DocProperties**に切り替えて、**文字列**ページを次の表に示すように、プロパティ ページ固有の項目を設定します。  
  
|アイテム|[値]|  
|----------|-----------|  
|Title|TextDocument|  
|ドキュメント文字列|VCUE TextDocument プロパティ|  
|Helpfile|*\<空白 >*|  
  
 呼び出すときにそのウィザードのこのページで設定した値がプロパティ ページのコンテナーに返される`IPropertyPage::GetPageInfo`します。 コンテナーに対する依存ですが、ユーザーに、ページを識別するために使用される通常後の文字列に動作します。 タイトルが、ページ上部のタブに表示されます、通常、およびドキュメント文字列は (ただし、標準のプロパティのフレームは、この文字列をまったく使用しない)、ステータス バーまたはツールヒントに表示される可能性があります。  
  
> [!NOTE]
>  ここで設定した文字列は、ウィザードによって、プロジェクトでの文字列リソースとして格納されます。 ページのコードが生成された後に、この情報を変更する必要がある場合は、リソース エディターを使用してこれらの文字列を簡単に編集できます。  
  
 をクリックして**OK**ウィザードで、プロパティ ページを生成します。  
  
##  <a name="vcconediting_the_dialog_resource"></a> ダイアログ リソースの編集  
 プロパティ ページが生成されたら、これで、いくつかのコントロール、ページを表すダイアログ リソースを追加する必要があります。 編集ボックス、静的テキスト コントロール、およびチェック ボックスを追加し、次に示すように、その Id を設定します。  
  
 ![ダイアログ リソースの編集](../atl/media/ppgresourcelabeled.gif "ppgresourcelabeled")  
  
 これらのコントロールは、ドキュメントとその読み取り専用状態のファイル名の表示に使用されます。  
  
> [!NOTE]
>  タブ付きファイルの場所を必要とする必要もダイアログ リソースは、フレームまたはコマンド ボタンは含まれません。 これらの機能は、呼び出すことによって作成されたものなどのプロパティ ページ フレームによって提供される[持つ](http://msdn.microsoft.com/library/windows/desktop/ms678437)します。  
  
##  <a name="vcconadding_message_handlers"></a> メッセージ ハンドラーを追加します。  
 インプレース コントロールとコントロールのいずれかの値が変更されたときに、ダーティ ページの状態を更新するメッセージ ハンドラーを追加できます。  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 このコードは呼び出すことで、編集コントロールまたはチェック ボックスをオンに加えられた変更に応答[IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty)ページが変更されたページのサイトに通知します。 ページのサイトを有効または無効に応答が通常、**適用**プロパティ ページ フレームのボタンをクリックします。  
  
> [!NOTE]
>  プロパティ ページには、正確にどのプロパティがユーザーによって変更されたが変更されていないプロパティの更新を回避できますを追跡する必要があります。 この例では、元のプロパティ値の追跡し、変更を適用する時間がある場合に、UI から現在の値と比較してそのコードを実装します。  
  
##  <a name="vcconhousekeeping"></a> ハウスキーピング  
 いくつかの追加`#import`DocProperties.h ステートメントについて、コンパイラが認識できるように、`Document`インターフェイス。  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 参照する必要も、`IPropertyPageImpl`基本クラスは、次の追加**typedef**を`CDocProperties`クラス。  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> ためにオーバーライドします。  
 最初の`IPropertyPageImpl`メソッドをオーバーライドする必要があるは[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)します。 ここでは、1 つのオブジェクトのみが渡されたことと、サポートしていることをチェックするコードを追加します、`Document`想定しているインターフェイス。  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  オブジェクトのファイル名を設定するユーザーを許可するために、このページの 1 つのオブジェクトのみをサポートするために合理的: 任意の 1 つの場所で 1 つのファイルが存在できます。  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> ためにオーバーライドします。  
 次の手順では、ページが最初に作成したときに基になるオブジェクトのプロパティ値を持つプロパティ ページを初期化します。  
  
 この場合、ページのユーザーがその変更を適用したときの比較プロパティの初期値に使用することもありますので、次のメンバーをクラスに追加する必要があります。  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 基本クラスの実装、[アクティブ化](../atl/reference/ipropertypageimpl-class.md#activate)メソッドは、このメソッドをオーバーライドして基底クラスを呼び出した後、独自の初期化処理を追加できるように、ダイアログ ボックスとそのコントロールの作成を担当します。  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 このコードの COM メソッドを使用して、`Document`に関心があるプロパティを取得するインターフェイス。 によって提供される Win32 API のラッパーを使用して、 [CDialogImpl](../atl/reference/cdialogimpl-class.md)とその基本クラスをユーザーに、プロパティの値を表示します。  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl::Apply をオーバーライドします。  
 ユーザーは、オブジェクトにその変更を適用する場合、プロパティ ページのサイトが呼び出す、[適用](../atl/reference/ipropertypageimpl-class.md#apply)メソッド。 これは、コードでの逆を行います`Activate`: 一方`Activate`オブジェクトから値を [プロパティ] ページで、コントロールにプッシュして`Apply`プロパティ ページのコントロールから値を取得し、プッシュに、オブジェクト。  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  に対してチェック[方](../atl/reference/ipropertypageimpl-class.md#m_bdirty)場合に、オブジェクトの不要な更新を回避するために最初のチェックは、この実装の先頭に`Apply`1 回以上呼び出されます。 チェックの各メソッドの呼び出しで結果の変更のみことを確認するプロパティの値に対しても、`Document`します。  
  
> [!NOTE]
> `Document` 公開`FullName`読み取り専用プロパティとして。 プロパティ ページに加えられた変更に基づいて、ドキュメントのファイル名を更新するを使用する必要がある、`Save`メソッドを別の名前でファイルを保存します。 自体を制限するプロパティ ページのコードはありませんので、取得または設定のプロパティにします。  
  
##  <a name="vccontesting_the_property_page"></a> プロパティ ページを表示します。  
 このページを表示するには、単純なヘルパー オブジェクトを作成する必要があります。 ヘルパー オブジェクトが簡素化するメソッドを提供、 `OleCreatePropertyFrame` 1 つのページを表示するための API が 1 つのオブジェクトに接続します。 このヘルパーは、Visual Basic から使用できるように設計されます。  
  
 使用して、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)と[ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)新しいクラスを生成して使用する`Helper`としてその短い名前。 作成されたら、次の表に示すように、メソッドを追加します。  
  
|アイテム|[値]|  
|----------|-----------|  
|メソッド名|`ShowPage`|  
|パラメーター|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 *BstrCaption*パラメーターは、ダイアログ ボックスのタイトルとして表示されるキャプション。 *BstrID*パラメーターは、CLSID または ProgID プロパティ ページの表示を表す文字列。 *PUnk*パラメーターになります、`IUnknown`プロパティ ページによって構成されるプロパティを持つオブジェクトのポインター。  
  
 次に示すように、メソッドを実装します。  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> マクロの作成  
 プロジェクトを作成したら、プロパティ ページと、ヘルパー オブジェクトを作成して、Visual Studio 開発環境で実行する単純なマクロを使用してテストできます。 このマクロは、ヘルパーを作成オブジェクトを呼び出してその`ShowPage`メソッドの ProgID を使用して、 **DocProperties**プロパティ ページ、 `IUnknown` Visual Studio エディターで現在アクティブなドキュメントのポインター。 このマクロに必要なコードは、以下に示します。  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
 
Public Module AtlPages  
 
    Public Sub Test()  
    Dim Helper  
    Helper = CreateObject("ATLPages7.Helper.1")  
 
    On Error Resume Next  
    Helper.ShowPage(_ 
    ActiveDocument.Name,
    _ 
 "ATLPages7Lib.DocumentProperties.1",
    _ 
    DTE.ActiveDocument _)  
    End Sub  
 
End Module  
```  
  
 このマクロを実行すると、ファイル名と現在アクティブなテキスト ドキュメントの読み取り専用の状態を示すプロパティ ページが表示されます。 ドキュメントの読み取り専用の状態は、開発環境でドキュメントに書き込む機能のみが反映されます。ディスク上のファイルの読み取り専用の属性には影響しません。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [例](../visual-cpp-samples.md)

