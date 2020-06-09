---
title: ATL (Active Template Library) の概念
ms.date: 05/06/2019
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
ms.openlocfilehash: cc96b5ed931713ca64a0582ca1cc18a8526ea8af
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616680"
---
# <a name="active-template-library-atl-concepts"></a>ATL (Active Template Library) の概念

Active Template Library (ATL) は、小さくて高速のコンポーネント オブジェクト モデル (COM) オブジェクトを作成できる、テンプレートに基づく C++ クラスのセットです。 ストックの実装、デュアル インターフェイス、標準 COM 列挙子インターフェイス、接続ポイント、ティアオフ インターフェイス、ActiveX コントロールなど、COM の重要な機能が特別にサポートされています。

ATL プログラミングを多用する場合は、COM プログラミングが簡単になるように設計されている COM と .NET の属性について、さらに詳しく学習する必要があります。 詳しくは、[Attributed Programming (属性付きプログラミング)](../windows/attributed-programming-concepts.md) に関するページをご覧ください。 (COM および .NET の属性を、C++ 標準\[\[attribute]] 機能と混同しないでください。)

## <a name="in-this-section"></a>このセクションの内容

[COM と ATL の概要](introduction-to-com-and-atl.md)<br/>
コンポーネント オブジェクト モデル (COM) の背後にある主要な概念について説明します。 ここでは、ATL とはどのようなもので、どういうときに使う必要があるかについても簡単に説明します。

[ATL COM オブジェクトの基礎](fundamentals-of-atl-com-objects.md)<br/>
さまざまな ATL クラスの間の関係と、それらのクラスを実装する方法について説明します。

[デュアルインターフェイスと ATL](dual-interfaces-and-atl.md)<br/>
ATL の観点からデュアル インターフェイスについて説明します。

[ATL のコレクションと列挙子](atl-collections-and-enumerators.md)<br/>
ATL でのコレクションと列挙子の実装および作成について説明します。

[複合コントロールの基本](atl-composite-control-fundamentals.md)<br/>
複合コントロールを作成する詳細な手順について説明します。 複合コントロールは、他の ActiveX コントロールまたは Windows コントロールを含むことができる ActiveX コントロールの種類です。

[ATL コントロールコンテインメントに関する FAQ](atl-control-containment-faq.md)<br/>
ATL でのコントロールのホストに関連する基本的な質問について説明します。

[ATL COM プロパティページ](atl-com-property-pages.md)<br/>
COM プロパティ ページを指定および実装する方法を示します。

[DHTML コントロールに対する ATL のサポート](atl-support-for-dhtml-controls.md)<br/>
DHTML コントロールを作成する詳細な手順について説明します。

[ATL コネクションポイント](atl-connection-points.md)<br/>
接続ポイントの概要と ATL での実装方法について説明します。

[イベント処理と ATL](event-handling-and-atl.md)<br/>
ATL の [IDispEventImpl](reference/idispeventimpl-class.md) および [IDispEventSimpleImpl](reference/idispeventsimpleimpl-class.md) クラスを使って COM イベントを処理するために必要な手順について説明します。

[ATL とフリースレッドマーシャラー](atl-and-the-free-threaded-marshaler.md)<br/>
独自のクラスでフリー スレッド マーシャラー (FTM) を集計できるようにする ATL シンプル オブジェクト ウィザードのオプションの詳細を説明します。

[プロジェクトのスレッド モデルの指定](specifying-the-threading-model-for-a-project-atl.md)<br/>
プロジェクトでのスレッドに関連する実行時のパフォーマンスの制御に使用できるマクロについて説明します。

[ATL モジュール クラス](atl-module-classes.md)<br/>
ATL 7.0 の新しいモジュール クラスについて説明します。 モジュール クラスでは、ATL で必要な基本機能が実装されています。

[ATL サービス](atl-services.md)<br/>
サービスが実装されるときに発生する一連のイベントについて説明します。 サービスの開発に関連する概念についても説明します。

[ATL ウィンドウクラス](atl-window-classes.md)<br/>
ATL でスーパークラス ウィンドウとサブクラス ウィンドウを作成する方法について説明します。 ATL ウィンドウ クラスは COM クラスではありません。

[ATL コレクションクラス](atl-collection-classes.md)<br/>
ATL で配列とマップを使用する方法について説明します。

[ATL レジストリ コンポーネント (レジストラー)](atl-registry-component-registrar.md)<br/>
ATL のスクリプト構文と置き換え可能パラメーターについて説明します。 また、レジストラーへの静的リンクを設定する方法も説明します。

[ATL および C ランタイム コードによるプログラミング](programming-with-atl-and-c-run-time-code.md)<br/>
C ランタイム ライブラリ (CRT) への静的または動的なリンクの利点について説明します。

[CComBSTR を使用したプログラミング](programming-with-ccombstr-atl.md)<br/>
`CComBSTR` でプログラミングするときに注意する必要のあるいくつかの状況について説明します。

[エンコーディングのリファレンス](atl-encoding-reference.md)<br/>
atlenc.h の uuencode、hexadecimal、UTF8 など、一般的なインターネット標準でのエンコードをサポートする関数とマクロを提供します。

[ユーティリティのリファレンス](atl-utilities-reference.md)<br/>
[CPathT](reference/cpatht-class.md) および [CUrl](reference/curl-class.md) の形式のパスと URL を操作するためのコードを提供します。 スレッド プール [CThreadPool](reference/cthreadpool-class.md) を独自のアプリケーションで使用できます。 このコードは、atlpath.h および atlutil.h に含まれます。

## <a name="related-sections"></a>関連項目

[ATL チュートリアル](active-template-library-atl-tutorial.md)<br/>
コントロールの作成手順について説明し、プロセスでの ATL の基本を示します。

[ATL のサンプル](../overview/visual-cpp-samples.md)<br/>
ATL のサンプル プログラムの説明とリンクを提供します。

[ATL プロジェクトの作成](reference/creating-an-atl-project.md)<br/>
ATL プロジェクト ウィザードについての説明が含まれます。

[ATL コントロール ウィザード](reference/atl-control-wizard.md)<br/>
クラスを追加する方法について説明します。

[属性付きプログラミング](../windows/attributed-programming-concepts.md)<br/>
属性を使って COM プログラミングを簡単にする方法の概要を説明し、さらに詳細なトピックへのリンクを提供します。

[ATL クラスの概要](atl-class-overview.md)<br/>
ATL クラスに関する参照情報とリンクを提供します。
