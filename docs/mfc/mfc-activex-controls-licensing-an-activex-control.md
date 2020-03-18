---
title: 'MFC ActiveX コントロール : ActiveX コントロールのライセンス'
ms.date: 11/19/2018
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: b08abdc0e2c17cb61c0c6a14cd712ec32ea816bd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438022"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのライセンス

ActiveX コントロールのオプション機能であるライセンスサポートを使用すると、コントロールを使用または配布できるユーザーを制御できます。 (ライセンスに関する問題の詳細については、「[既存の ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)に関する問題」を参照してください)。

> [!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

この記事では、次のトピックについて説明します。

- [ActiveX コントロールのライセンスの概要](#_core_overview_of_activex_control_licensing)

- [ライセンスされたコントロールの作成](#_core_creating_a_licensed_control)

- [ライセンスサポート](#_core_licensing_support)

- [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)

ライセンスを実装する ActiveX コントロールでは、コントロール開発者は、他のユーザーが ActiveX コントロールを使用する方法を決定できます。 コントロールの購入者には、コントロールとを指定します。契約書を使用する LIC ファイル。購入者がコントロールを配布することはできますが、は含まれません。LIC ファイル。コントロールを使用するアプリケーションが含まれています。 これにより、そのアプリケーションのユーザーは、最初にコントロールをライセンス認証することなく、コントロールを使用する新しいアプリケーションを作成できなくなります。

##  <a name="_core_overview_of_activex_control_licensing"></a>ActiveX コントロールのライセンスの概要

ActiveX コントロールのライセンスサポートを提供するために、 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)クラスは、`IClassFactory2::RequestLicKey`、`IClassFactory2::GetLicInfo`、および `IClassFactory2::CreateInstanceLic`の `IClassFactory2` インターフェイス内のいくつかの関数の実装を提供します。 コンテナーアプリケーションの開発者がコントロールのインスタンスを作成するように要求すると、そのコントロールを確認するための `GetLicInfo` の呼び出しが行われます。LIC ファイルが存在します。 コントロールがライセンスされている場合は、コントロールのインスタンスを作成し、コンテナーに配置できます。 開発者がコンテナーアプリケーションの構築を完了すると、もう1つの関数呼び出しが行われます。この時間は `RequestLicKey`になります。 この関数は、ライセンスキー (単純な文字列) をコンテナーアプリケーションに返します。 返されたキーは、アプリケーションに埋め込まれます。

次の図は、コンテナーアプリケーションの開発中に使用される ActiveX コントロールのライセンス検証を示しています。 既に説明したように、コンテナーアプリケーションの開発者には適切なが必要です。コントロールのインスタンスを作成するために開発用コンピューターにインストールされた LIC ファイル。

![開発時に検証されたライセンスされた ActiveX コントロール](../mfc/media/vc374d1.gif "開発時で検証された、ライセンスされた ActiveX コントロール") <br/>
開発時の ActiveX コントロールのライセンス検査

次の図に示すように、エンドユーザーがコンテナーアプリケーションを実行すると、次のプロセスが発生します。

アプリケーションが開始されると、通常、コントロールのインスタンスを作成する必要があります。 コンテナーは、`CreateInstanceLic`を呼び出して、埋め込みライセンスキーをパラメーターとして渡すことによってこれを実現します。 次に、埋め込みライセンスキーと、ライセンスキーのコントロール独自のコピーとの間で文字列比較が行われます。 一致が成功した場合、コントロールのインスタンスが作成され、アプリケーションは正常に実行され続けます。 であることに注意してください。LIC ファイルがコントロールユーザーのコンピューターに存在していない必要があります。

![実行時に検証されたライセンスされた ActiveX コントロール](../mfc/media/vc374d2.gif "実行時に検証された、ライセンスされた ActiveX コントロール") <br/>
実行時の ActiveX コントロールのライセンス検査

コントロールのライセンスは、コントロール実装 DLL 内の特定のコードとライセンスファイルの2つの基本的なコンポーネントで構成されています。 このコードは、2つ (または 3) の関数呼び出しと、著作権に関する通知を含む "ライセンス文字列" と呼ばれる文字列で構成されます。 これらの呼び出しとライセンス文字列は、コントロールの実装にあります (「」を参照してください。CPP) ファイル。 ActiveX コントロールウィザードによって生成されるライセンスファイルは、著作権に関する声明を含むテキストファイルです。 これには、プロジェクト名とを使用して名前が付けられます。LIC extension (例)。LIC. デザイン時の使用が必要な場合は、ライセンスされたコントロールにライセンスファイルを添付する必要があります。

##  <a name="_core_creating_a_licensed_control"></a>ライセンスされたコントロールの作成

ActiveX コントロールウィザードを使用してコントロールフレームワークを作成する場合、ライセンスサポートを簡単に含めることができます。 コントロールにランタイムライセンスが必要であることを指定すると、ActiveX コントロールウィザードによって、ライセンスをサポートするためのコードがコントロールクラスに追加されます。 このコードは、ライセンス認証のためにキーとライセンスファイルを使用する関数で構成されています。 これらの関数を変更して、コントロールのライセンスをカスタマイズすることもできます。 ライセンスのカスタマイズの詳細については、この記事で後述する「 [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>ActiveX コントロールウィザードを使用して、コントロールプロジェクトを作成するときにライセンスのサポートを追加するには

1. 「 [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)」の手順を使用します。 ActiveX コントロールウィザードの **[アプリケーションの設定]** ページには、ランタイムライセンスを持つコントロールを作成するオプションがあります。

ActiveX コントロールウィザードで、基本的なライセンスサポートを含む ActiveX コントロールフレームワークが生成されるようになりました。 ライセンスコードの詳細については、次のトピックを参照してください。

##  <a name="_core_licensing_support"></a>ライセンスサポート

Activex コントロールウィザードを使用して ActiveX コントロールにライセンスサポートを追加すると、ActiveX コントロールウィザードによって、ライセンス機能を宣言して実装するコードが追加され、コントロールのヘッダーおよび実装ファイルに追加されます。 このコードは、`VerifyUserLicense` のメンバー関数と、 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)の既定の実装をオーバーライドする `GetLicenseKey` メンバー関数で構成されています。 これらの関数は、コントロールのライセンスを取得して確認します。

> [!NOTE]
>  3番目のメンバー関数 `VerifyLicenseKey` は ActiveX コントロールウィザードでは生成されませんが、オーバーライドしてライセンスキーの検証動作をカスタマイズできます。

これらのメンバー関数は次のとおりです。

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   コントロールで、コントロールのライセンスファイルが存在するかどうかを確認することによって、デザイン時の使用を許可するかどうかを確認します。 この関数は、`IClassFactory2::GetLicInfo` と `IClassFactory::CreateInstanceLic`の処理の一部としてフレームワークによって呼び出されます。

- [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   コントロール DLL から一意のキーを要求します。 このキーはコンテナーアプリケーションに埋め込まれ、後で `VerifyLicenseKey`と組み合わせて使用して、コントロールのインスタンスを作成します。 この関数は、`IClassFactory2::RequestLicKey`の処理の一部としてフレームワークによって呼び出されます。

- [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   埋め込まれたキーとコントロールの一意のキーが同じであることを確認します。 これにより、コンテナーは使用するコントロールのインスタンスを作成できます。 この関数は、`IClassFactory2::CreateInstanceLic` の処理の一部としてフレームワークによって呼び出され、ライセンスキーのカスタマイズされた検証を行うためにオーバーライドできます。 既定の実装では、文字列比較が実行されます。 詳細については、この記事で後述する「 [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

###  <a name="_core_header_file_modifications"></a>ヘッダーファイルの変更

ActiveX コントロールウィザードでは、次のコードがコントロールヘッダーファイルに配置されます。 この例では、`CSampleCtrl`のオブジェクト `factory` の2つのメンバー関数が宣言されています。1つはコントロールの存在を検証する関数です。LIC ファイルと、コントロールを含むアプリケーションで使用されるライセンスキーを取得する別のファイル。

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

###  <a name="_core_implementation_file_modifications"></a>実装ファイルの変更

ActiveX コントロールウィザードでは、ライセンスファイル名とライセンス文字列を宣言するために、コントロール実装ファイルに次の2つのステートメントが配置されます。

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
>  何らかの方法で `szLicString` を変更する場合は、コントロールの最初の行も変更する必要があります。LIC ファイルまたはライセンスは正常に機能しません。

ActiveX コントロールウィザードでは、コントロールクラス ' `VerifyUserLicense` および `GetLicenseKey` 関数を定義するために、コントロール実装ファイルに次のコードを配置します。

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

最後に、 **ActiveX コントロールウィザード**によって、コントロールプロジェクトが変更されます。IDL ファイル。 **ライセンス**されたキーワードは、次の例のように、コントロールのコクラス宣言に追加されます。

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX コントロールのライセンスのカスタマイズ

`VerifyUserLicense`、`GetLicenseKey`、および `VerifyLicenseKey` は、コントロールファクトリクラスの仮想メンバー関数として宣言されているため、コントロールのライセンスの動作をカスタマイズできます。

たとえば、`VerifyUserLicense` または `VerifyLicenseKey` のメンバー関数をオーバーライドすることによって、コントロールに複数のレベルのライセンスを提供できます。 この関数内では、検出されたライセンスレベルに従って、ユーザーに公開されるプロパティまたはメソッドを調整できます。

また、コントロールの作成が失敗したことをユーザーに通知するためのカスタマイズされたメソッドを提供する、`VerifyLicenseKey` 関数にコードを追加することもできます。 たとえば、`VerifyLicenseKey` メンバー関数では、コントロールの初期化に失敗したこととその理由を示すメッセージボックスを表示できます。

> [!NOTE]
>  ActiveX コントロールライセンスの検証をカスタマイズするもう1つの方法は、`AfxVerifyLicFile`を呼び出すのではなく、特定のレジストリキーの登録データベースをチェックすることです。 既定の実装の例については、この記事の「[実装ファイルの変更](#_core_implementation_file_modifications)」セクションを参照してください。

ライセンスに関する問題の詳細については、「[既存の ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)に関する問題」を参照してください。

## <a name="see-also"></a>参照

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)
