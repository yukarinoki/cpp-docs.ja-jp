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
ms.openlocfilehash: aaab4ae3bb13790784a66d53b41dbc3a7cdaec89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364612"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのライセンス

ActiveX コントロールのオプション機能であるライセンス サポートでは、コントロールを使用または配布できるユーザーを制御できます。 (ライセンスに関するその他の説明については、既存の[ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)のライセンスに関する問題を参照してください)。

> [!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

この記事では、次のトピックについて説明します。

- [ActiveX コントロール ライセンスの概要](#_core_overview_of_activex_control_licensing)

- [ライセンスコントロールの作成](#_core_creating_a_licensed_control)

- [ライセンスサポート](#_core_licensing_support)

- [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)

ライセンスを実装する ActiveX コントロールを使用すると、コントロール開発者は、他のユーザーが ActiveX コントロールをどのように使用するかを決定できます。 コントロールの購入者に コントロールと を提供します。LIC ファイルは、購入者がコントロールを配布する可能性がありますが、 は配布しないことを同意します。LIC ファイルで、コントロールを使用するアプリケーションを含みます。 これにより、コントロールを最初にライセンスを取得せずに、そのアプリケーションのユーザーがコントロールを使用する新しいアプリケーションを作成できなくなります。

## <a name="overview-of-activex-control-licensing"></a><a name="_core_overview_of_activex_control_licensing"></a>ActiveX コントロール ライセンスの概要

ActiveX コントロールのライセンス サポートを提供するために[、COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)クラスは`IClassFactory2`、インターフェイス内のいくつかの関数の実装`IClassFactory2::RequestLicKey``IClassFactory2::GetLicInfo`を提供`IClassFactory2::CreateInstanceLic`します。 コンテナー アプリケーションの開発者がコントロールのインスタンスを作成する要求を行うと、 コントロール`GetLicInfo`の呼び出しが行われ、コントロール が呼び出されます。LIC ファイルが存在します。 コントロールがライセンスされている場合、コントロールのインスタンスを作成してコンテナーに配置できます。 開発者がコンテナアプリケーションの構築を終了すると、今度`RequestLicKey`は別の関数呼び出しが行われます。 この関数は、コンテナ アプリケーションにライセンス キー (単純な文字列) を返します。 返されたキーは、アプリケーションに埋め込まれます。

次の図は、コンテナ アプリケーションの開発中に使用される ActiveX コントロールのライセンス検証を示しています。 前述のように、コンテナ アプリケーション開発者は適切な .コントロールのインスタンスを作成するために開発マシンにインストールされた LIC ファイル。

![開発時で検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d1.gif "開発時で検証された、ライセンスされた ActiveX コントロール") <br/>
開発時の ActiveX コントロールのライセンス検査

次のプロセスは、次の図に示すように、エンド ユーザーがコンテナー アプリケーションを実行するときに発生します。

アプリケーションが起動されると、通常はコントロールのインスタンスを作成する必要があります。 コンテナーは、 に`CreateInstanceLic`呼び出しを行うことでこれを実現し、埋め込みライセンス キーをパラメーターとして渡します。 次に、埋め込みライセンス キーとコントロール自身のライセンス キーのコピーとの間で文字列比較が行われます。 一致が成功すると、コントロールのインスタンスが作成され、アプリケーションは正常に実行されます。 に注意してください。LIC ファイルは、制御ユーザーのマシン上に存在する必要はありません。

![実行時に検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d2.gif "実行時に検証された、ライセンスされた ActiveX コントロール") <br/>
実行時の ActiveX コントロールのライセンス検査

コントロール ライセンスは、コントロール実装 DLL の特定のコードとライセンス ファイルの 2 つの基本コンポーネントで構成されます。 コードは、2 つの (または 3 つ) の関数呼び出しと文字列で構成され、次に「ライセンス文字列」と呼ばれ、著作権表示が含まれます。 これらの呼び出しとライセンス文字列は、コントロールの実装 (.CPP) ファイル。 ActiveX コントロール ウィザードによって生成されるライセンス ファイルは、著作権に関する記述を含むテキスト ファイルです。 プロジェクト名を使用して、 という名前が付けられます。LIC 拡張例として、サンプル。Lic。 デザイン時の使用が必要な場合は、ライセンス・コントロールにライセンス・ファイルを伴う必要があります。

## <a name="creating-a-licensed-control"></a><a name="_core_creating_a_licensed_control"></a>ライセンスコントロールの作成

ActiveX コントロール ウィザードを使用してコントロール フレームワークを作成すると、ライセンスサポートを簡単に含めることができます。 コントロールにランタイム ライセンスを付与するように指定すると、ActiveX コントロール ウィザードは、ライセンスをサポートするコードをコントロール クラスに追加します。 コードは、ライセンス検証にキーとライセンスファイルを使用する機能で構成されています。 これらの機能は、コントロール ライセンスをカスタマイズするために変更することもできます。 ライセンスのカスタマイズの詳細については、この記事[の「ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>コントロール プロジェクトの作成時に ActiveX コントロール ウィザードを使用してライセンスのサポートを追加するには

1. [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)の手順を使用します。 ActiveX コントロール ウィザードの **[アプリケーションの設定]** ページには、ランタイム ライセンスを使用してコントロールを作成するオプションがあります。

ActiveX コントロール ウィザードは、基本的なライセンス サポートを含む ActiveX コントロール フレームワークを生成するようになりました。 ライセンス コードの詳細については、次のトピックを参照してください。

## <a name="licensing-support"></a><a name="_core_licensing_support"></a>ライセンスサポート

ActiveX コントロール ウィザードを使用して ActiveX コントロールにライセンス サポートを追加すると、ActiveX コントロール ウィザードによって、ライセンス機能を宣言および実装するコードがコントロール ヘッダー ファイルと実装ファイルに追加されます。 このコードは、`VerifyUserLicense`メンバー関数と`GetLicenseKey`メンバー関数で構成され[、COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)の既定の実装をオーバーライドします。 これらの関数は、制御ライセンスを取得して検証します。

> [!NOTE]
> 3 つ目の`VerifyLicenseKey`メンバー関数は ActiveX コントロール ウィザードによって生成されませんが、ライセンス キーの検証動作をカスタマイズするためにオーバーライドできます。

これらのメンバー関数は次のとおりです。

- [ユーザーライセンスの確認](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   コントロールがコントロール ライセンス ファイルの存在をシステムでチェックすることによって、コントロールがデザイン時の使用を許可していることを確認します。 この関数は、フレームワークによって処理`IClassFactory2::GetLicInfo`の一部として呼`IClassFactory::CreateInstanceLic`び出されます。

- [ライセンスキーを取得します。](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   コントロール DLL に一意のキーを要求します。 このキーはコンテナー アプリケーションに埋め込まれ、後で`VerifyLicenseKey`と組み合わせて使用され、コントロールのインスタンスを作成します。 この関数は、処理`IClassFactory2::RequestLicKey`の一部としてフレームワークによって呼び出されます。

- [ライセンスキーの確認](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   埋め込みキーとコントロールの一意のキーが同じであることを確認します。 これにより、コンテナーは、その使用するコントロールのインスタンスを作成できます。 この関数は、フレームワークによって処理`IClassFactory2::CreateInstanceLic`の一部として呼び出され、ライセンス キーのカスタマイズされた検証を提供するためにオーバーライドできます。 既定の実装では、文字列比較を実行します。 詳細については、この記事[の「 ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

### <a name="header-file-modifications"></a><a name="_core_header_file_modifications"></a>ヘッダー ファイルの変更

ActiveX コントロール ウィザードは、コントロール ヘッダー ファイルに次のコードを配置します。 この例では、 ' の`CSampleCtrl`オブジェクト`factory`の 2 つのメンバー関数が宣言されています。LIC ファイルと、コントロールを含むアプリケーションで使用するライセンス キーを取得するファイル:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

### <a name="implementation-file-modifications"></a><a name="_core_implementation_file_modifications"></a>実装ファイルの変更

ActiveX コントロール ウィザードでは、次の 2 つのステートメントをコントロール実装ファイルに配置して、ライセンス ファイル名とライセンス文字列を宣言します。

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
> 何らかの方法`szLicString`で変更する場合は、コントロールの最初の行も変更する必要があります。LICファイルまたはライセンスは正しく機能しません。

ActiveX コントロール ウィザードは、コントロールの実装ファイルに次のコードを配置して、`VerifyUserLicense`コントロール`GetLicenseKey`クラスと関数を定義します。

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

最後に **、ActiveX コントロール ウィザード**によってコントロール プロジェクトが変更されます。IDL ファイル。 次の例のように、**ライセンスされた**キーワードがコントロールのコクラス宣言に追加されます。

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

## <a name="customizing-the-licensing-of-an-activex-control"></a><a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX コントロールのライセンスのカスタマイズ

、`VerifyUserLicense``GetLicenseKey`および`VerifyLicenseKey`はコントロール ファクトリ クラスの仮想メンバー関数として宣言されているため、コントロールのライセンス動作をカスタマイズできます。

たとえば、`VerifyUserLicense`または`VerifyLicenseKey`メンバー関数をオーバーライドすることによって、コントロールに対して複数のレベルのライセンスを提供できます。 この関数の内部では、検出したライセンス レベルに応じて、ユーザーに公開するプロパティまたはメソッドを調整できます。

また、コントロールの作成が`VerifyLicenseKey`失敗したことをユーザーに通知するカスタマイズされたメソッドを提供するコードを関数に追加することもできます。 たとえば、`VerifyLicenseKey`メンバ関数では、コントロールが初期化に失敗した理由とその理由を示すメッセージ ボックスを表示できます。

> [!NOTE]
> ActiveX コントロール ライセンスの検証をカスタマイズするもう 1 つの方法は、 を呼び出`AfxVerifyLicFile`す代わりに、特定のレジストリ キーの登録データベースをチェックすることです。 既定の実装の例については、この記事の[「実装ファイルの変更](#_core_implementation_file_modifications)」セクションを参照してください。

ライセンスに関するその他の問題については、既存の[ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)のライセンスに関する問題を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)
