---
title: Active Template Library (ATL) の概念 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5636f92df42116b838c24c21d81f0b320f7d69c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="active-template-library-atl-concepts"></a>ATL (Active Template Library) の概念
アクティブ テンプレート ライブラリ (ATL) は、小規模で高速のコンポーネント オブジェクト モデル (COM) オブジェクトを作成するのに便利なテンプレート ベースの C++ クラスのセットです。 ストックの実装、デュアル インターフェイス、標準の COM 列挙子インターフェイス、接続ポイント、ティアオフ インターフェイス、および ActiveX コントロールを含むキーの COM 機能用の特別なサポートしています。  
  
 ATL プログラミングの多くを実行する場合は、詳細については、属性、COM プログラミングを簡略化するように設計された Visual C .NET の新機能はします。 詳細については、次を参照してください。[属性付きプログラミング](../windows/attributed-programming-concepts.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)  
 コントロールの作成について説明し、プロセスで、ATL の基本事項をいくつかを示します。  
  
 [COM と ATL の概要](../atl/introduction-to-com-and-atl.md)  
 コンポーネント オブジェクト モデル (COM) の背後にある主な概念を紹介します。 この記事には、ATL とそれを使用する際も簡単に説明します。  
  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)  
 さまざまな ATL クラスおよびそれらのクラスを実装する方法の関係について説明します。  
  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)  
 ATL の観点からデュアル インターフェイスをについて説明します。  
  
 [ATL のコレクションと列挙子](../atl/atl-collections-and-enumerators.md)  
 実装およびコレクションと ATL の列挙子の作成について説明します  
  
 [複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)  
 複合コントロールの作成の詳細な手順についてを説明します。 複合コントロールは、他の ActiveX コントロールまたは Windows のコントロールを含めることができる ActiveX コントロールの種類です。  
  
 [ATL コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)  
 カバー ATL. を持つコントロールのホスティングに関連する基本的な質問  
  
 [ATL COM プロパティ ページ](../atl/atl-com-property-pages.md)  
 指定して、COM プロパティ ページを実装する方法を示します。  
  
 [DHTML コントロールの ATL サポート](../atl/atl-support-for-dhtml-controls.md)  
 DHTML コントロールの作成の詳細な手順についてを説明します。  
  
 [ATL コネクション ポイント](../atl/atl-connection-points.md)  
 コネクション ポイントの概要と ATL での実装方法について説明します。  
  
 [イベント処理と ATL](../atl/event-handling-and-atl.md)  
 ATL を使用して COM イベントを処理するために必要な手順について説明します[IDispEventImpl](../atl/reference/idispeventimpl-class.md)と[されます](../atl/reference/idispeventsimpleimpl-class.md)クラスです。  
  
 [ATL とフリー スレッド マーシャラー](../atl/atl-and-the-free-threaded-marshaler.md)  
 フリー スレッド マーシャラー (FTM) を集計するクラスを許可する、ATL シンプル オブジェクト ウィザードのオプションについて説明します。  
  
 [プロジェクトのスレッド モデルの指定](../atl/specifying-the-threading-model-for-a-project-atl.md)  
 プロジェクトでのスレッドに関連する実行時のパフォーマンスを制御する使用可能なマクロについて説明します。  
  
 [ATL モジュール クラス](../atl/atl-module-classes.md)  
 ATL 7.0 の新しいモジュール クラスについて説明します。 モジュールのクラスは ATL で必要な基本機能を実装します。  
  
 [ATL サービス](../atl/atl-services.md)  
 一連のサービスが実装されているときに発生するイベントについて説明します。 いくつかのサービスの開発に関連する概念についても説明します。  
  
 [ATL ウィンドウ クラス](../atl/atl-window-classes.md)  
 作成する方法、スーパークラスと ATL でサブクラス ウィンドウについて説明します ATL ウィンドウ クラスは、COM クラスではありません。  
  
 [ATL コレクション クラス](../atl/atl-collection-classes.md)  
 配列を使用する方法について説明し、ATL のマップ  
  
 [ATL レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)  
 ATL スクリプト構文と置き換え可能パラメーターをについて説明します。 レジストラーに静的にリンクを設定する方法についても説明します。  
  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)  
 静的または動的に C ランタイム ライブラリ (CRT) へのリンクの利点について説明します。  
  
 [CComBSTR を使用したプログラミング](../atl/programming-with-ccombstr-atl.md)  
 プログラミングする際の注意を必要とするいくつかの状況について説明します`CComBSTR`です。  
  
 [エンコーディングのリファレンス](../atl/atl-encoding-reference.md)  
 関数とマクロ atlenc.h で uuencode、16 進数などの一般的なインターネット標準の範囲および UTF8 でエンコードのサポートを提供します。  
  
 [ユーティリティのリファレンス](../atl/atl-utilities-reference.md)  
 形式でパスと Url を操作するコードを提供[CPathT](../atl/reference/cpatht-class.md)と[CUrl](../atl/reference/curl-class.md)です。 スレッド プール、 [CThreadPool](../atl/reference/cthreadpool-class.md)、独自のアプリケーションで使用できます。 このコードは、atlpath.h と atlutil.h 含まれています。  
  
## <a name="related-sections"></a>関連項目  
 [ATL のサンプル](../visual-cpp-samples.md)  
 説明と ATL のサンプル プログラムへのリンクを提供します。  
  
 [ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
 ATL プロジェクト ウィザードについてを説明します。  
  
 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)  
 クラスを追加する方法について説明します。  
  
 [属性付きプログラミング](../windows/attributed-programming-concepts.md)  
 属性を使用して、COM プログラミングの詳細なトピックへのリンクの一覧を簡略化する方法の概要を示します。  
  
 [ATL のクラスの概要](../atl/atl-class-overview.md)  
 参照情報と ATL クラスへのリンクを提供します。

