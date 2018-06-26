---
title: 'MFC ActiveX コントロール: ActiveX コントロールのライセンス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COleObjectFactory
dev_langs:
- C++
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0b1e8f0c54cf4d409aedb99fc3195b927d5f127
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929745"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのライセンス
ライセンスのサポート、ActiveX コントロールのオプション機能を制御できますを使用して、コントロールを配布したりできるユーザーをします。 (ライセンスの問題の詳細については、ライセンスの問題を参照してください[既存の ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)。)。  
  
 この記事では、次のトピックについて説明します。  
  
-   [ActiveX コントロールのライセンスの概要](#_core_overview_of_activex_control_licensing)  
  
-   [ライセンスされたコントロールを作成します。](#_core_creating_a_licensed_control)  
  
-   [ライセンスのサポート](#_core_licensing_support)  
  
-   [ActiveX コントロールのライセンスをカスタマイズします。](#_core_customizing_the_licensing_of_an_activex_control)  
  
 ライセンスを実装する ActiveX コントロールでは、他のユーザーが ActiveX コントロールを使用する方法を決定する、コントロール開発者として使用する、できます。 コントロールにコントロールの購入者を指定するとします。購入した顧客配布することが、コントロールしない場合は、アグリーメントでの使用許諾契約書ファイル、します。コントロールを使用するアプリケーションでの使用許諾契約書ファイルです。 これは、最初のライセンスを制御することがなく、コントロールを使用する新しいアプリケーションの作成からそのアプリケーションのようにします。  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX コントロールのライセンスの概要  
 ActiveX コントロールのライセンスをサポートする、 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)クラスにいくつかの関数の実装を提供、`IClassFactory2`インターフェイス: `IClassFactory2::RequestLicKey`、 `IClassFactory2::GetLicInfo`、および`IClassFactory2::CreateInstanceLic`です。 コンテナー アプリケーションの開発者が、コントロールへの呼び出しのインスタンスを作成する要求を行うときに`GetLicInfo`されることを確認するコントロール。使用許諾契約書ファイルが存在します。 コントロールのライセンスが与えられた場合、コントロールのインスタンスが作成され、コンテナーに配置することができます。 開発者は、コンテナー アプリケーションの構築が終了したら、別の関数を呼び出すには、この時間`RequestLicKey`が行われます。 この関数は、コンテナー アプリケーションにライセンス キー (単純な文字列) を返します。 返されたキーは、アプリケーションで埋め込まれます。  
  
 次の図では、ActiveX コントロール コンテナー アプリケーションの開発時に使用されるライセンスの確認を示します。 前述のように、コンテナー アプリケーションの開発者には、適切な必要があります。コントロールのインスタンスを作成する開発用コンピューターにインストールされている使用許諾契約書ファイルです。  
  
 ![ライセンスされた ActiveX コントロールの開発時に検証](../mfc/media/vc374d1.gif "vc374d1")  
開発時の ActiveX コントロールのライセンス検査  
  
 次の図に示すように、次のプロセスは、エンドユーザーは、コンテナー アプリケーションを実行するときに発生します。  
  
 アプリケーションが開始されたときに、コントロールのインスタンス通常作成が必要です。 コンテナーへの呼び出しでは`CreateInstanceLic`、埋め込まれているライセンス キーをパラメーターとして渡します。 文字列の比較が区別し、埋め込まれているライセンス キーとライセンス キーのコントロールのコピーします。 一致が成功した場合は、コントロールのインスタンスが作成され、アプリケーションは正常に実行を継続します。 なお、します。使用許諾契約書ファイルは、コントロールのユーザーのコンピューターに存在していない必要があります。  
  
 ![ライセンスされた ActiveX コントロールの実行時に検証](../mfc/media/vc374d2.gif "vc374d2")  
実行時の ActiveX コントロールのライセンス検査  
  
 コントロールのライセンスの 2 つの基本的なコンポーネントで構成されています: コントロールの実装 DLL 内の特定のコードとライセンス ファイル。 コードは、次の 2 つ (または 3 つ) の関数呼び出しと、「ライセンス文字列」、著作権の通知を含むと呼ぶ文字列で構成されます。 これらの呼び出しとライセンスの文字列は、「コントロールの実装 (です。CPP) ファイルです。 ActiveX コントロール ウィザードによって生成されたライセンス ファイルは、著作権表記を含むテキスト ファイルです。 名前は、プロジェクト名に、します。使用許諾契約書の拡張機能、サンプルの使用例です。使用許諾契約書です。 ライセンスされたコントロール付属していなければなりませんライセンス ファイルに、デザイン時の使用が必要な場合です。  
  
##  <a name="_core_creating_a_licensed_control"></a> ライセンスされたコントロールを作成します。  
 コントロールのフレームワークを作成する ActiveX コントロール ウィザードを使用する場合は、ライセンス サポート簡単です。 コントロールが実行時ライセンスを持つ必要がありますを指定する場合、ActiveX コントロール ウィザードは、ライセンスをサポートするために、コントロール クラスにコードを追加します。 ライセンス検証キーとライセンス ファイルを使用する関数のコードで構成されます。 これらの関数を変更してコントロールのライセンスをカスタマイズすることができます。 ライセンスのカスタマイズの詳細については、次を参照してください。[ライセンス ActiveX コントロールのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)この記事で後述します。  
  
#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>コントロール プロジェクトを作成するときに、ActiveX コントロール ウィザードを使用してライセンスのサポートを追加するには  
  
1.  」の指示に従って[MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)です。 **アプリケーション設定**ActiveX コントロール ウィザードのページには、実行時ライセンスを持つコントロールを作成するオプションが含まれています。  
  
 今すぐ、ActiveX コントロール ウィザードには、基本ライセンス サポートを含む ActiveX コントロールのフレームワークが生成されます。 ライセンス コードの詳細については、次のトピックを参照してください。  
  
##  <a name="_core_licensing_support"></a> ライセンスのサポート  
 ActiveX コントロール ウィザードを使用して、ActiveX コントロール ライセンス サポートを追加すると、ActiveX コントロール ウィザードを宣言し、ライセンスの機能を実装するコードが追加、コントロールのヘッダーおよび実装するファイルを追加します。 このコードは、`VerifyUserLicense`メンバー関数および`GetLicenseKey`については、既定の実装をオーバーライドするメンバー関数[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)です。 これらの関数は、取得し、コントロールのライセンスを確認します。  
  
> [!NOTE]
>  3 番目のメンバー関数では、`VerifyLicenseKey`は ActiveX コントロール ウィザードによって生成されませんが、ライセンス キーの検証動作をカスタマイズするをオーバーライドすることができます。  
  
 これらのメンバー関数は次のとおりです。  
  
-   [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)  
  
     コントロールでは、デザイン時の使用方法によって、コントロールのライセンス ファイルのシステムに存在することを確認することを確認します。 この関数`IClassFactory2::GetLicInfo`と`IClassFactory::CreateInstanceLic`です。  
  
-   [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)  
  
     コントロールの DLL からの一意のキーを要求します。 このキーはコンテナー アプリケーションの埋め込みデータ ソースとと共に、後で、使用`VerifyLicenseKey`コントロールのインスタンスを作成します。 この関数`IClassFactory2::RequestLicKey`です。  
  
-   [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)  
  
     埋め込まれたキーと、コントロールの一意のキーは、同じであることを確認します。 これにより、コンテナーの使用のためのコントロールのインスタンスを作成できます。 この関数`IClassFactory2::CreateInstanceLic`ライセンス キーの確認方法をカスタマイズするオーバーライドすることができます。 既定の実装では、文字列比較を実行します。 詳細については、次を参照してください。[ライセンス ActiveX コントロールのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)、この記事で後述します。  
  
###  <a name="_core_header_file_modifications"></a> ヘッダー ファイルの変更  
 ActiveX コントロール ウィザードでは、コントロールのヘッダー ファイルに次のコードを配置します。 この例の 2 つのメンバー関数で`CSampleCtrl`オブジェクト 's`factory`宣言され、コントロールが存在することを検証します。使用許諾契約書ファイル、およびコントロールを含むアプリケーションで使用するライセンス キーを取得します。  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> 実装ファイルの変更  
 ActiveX コントロール ウィザードでは、次の 2 つのステートメントをライセンス ファイル名とライセンスの文字列を宣言する、コントロール実装ファイルに配置します。  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  変更した場合`szLicString`何らかの方法では、コントロールの最初の行も変更する必要があります。使用許諾契約書ファイルまたはライセンスは正しく機能しません。  
  
 ActiveX コントロール ウィザードは、コントロール クラスの定義に、コントロール実装ファイルに次のコードを配置`VerifyUserLicense`と`GetLicenseKey`関数。  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 最後に、 **ActiveX コントロール ウィザード**コントロール プロジェクトを変更します。IDL ファイルです。 **ライセンス**キーワードを次の例のように、コントロールのコクラスの宣言に追加します。  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> ActiveX コントロールのライセンスをカスタマイズします。  
 `VerifyUserLicense`、 `GetLicenseKey`、および`VerifyLicenseKey`コントロール ファクトリ クラスの仮想メンバー関数として宣言は、コントロールのライセンスの動作をカスタマイズすることができます。  
  
 オーバーライドすることで、コントロールのライセンスのいくつかのレベルを指定するなど、`VerifyUserLicense`または`VerifyLicenseKey`メンバー関数。 この関数の内部検出したライセンス レベルに従ってユーザーに公開するプロパティやメソッドを調整できます。  
  
 コードを追加することも、`VerifyLicenseKey`作成を制御するユーザーに通知が失敗したためにカスタマイズしたメソッドを提供する関数。 インスタンスで、`VerifyLicenseKey`メンバー関数は、メッセージを表示する可能性がありますが、コントロールが初期化に失敗したことを示すをボックスおよびその理由です。  
  
> [!NOTE]
>  呼び出す代わりに、特定のレジストリ キーの登録データベースを確認する ActiveX コントロールのライセンスの検証をカスタマイズする方法は、`AfxVerifyLicFile`です。 既定の実装の例は、次を参照してください。、[実装ファイルの変更](#_core_implementation_file_modifications)この記事のセクションです。  
  
 ライセンスの問題の詳細については、ライセンスの問題を参照してください。[既存の ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)

