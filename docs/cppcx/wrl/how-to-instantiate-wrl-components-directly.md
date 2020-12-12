---
description: '詳細については、「方法: WRL コンポーネントを直接インスタンス化する」を参照してください。'
title: '方法: WRL コンポーネントを直接インスタンス化する'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 424b3ec70921de9558fd8c5035e96b2fe4d58f7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249894"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>方法: WRL コンポーネントを直接インスタンス化する

Windows ランタイム C++ テンプレートライブラリ (WRL)[microsoft:: wrl:: Make](make-function.md) および [microsoft:: wrl::D Etails:: makeandinitialize](makeandinitialize-function.md) 関数を使用して、コンポーネントを定義するモジュールからコンポーネントをインスタンス化する方法について説明します。

コンポーネントを直接インスタンス化することにより、クラス ファクトリやその他の機構が必要ない場合にオーバーヘッドを低減できます。 コンポーネントは、ユニバーサル Windows プラットフォームアプリとデスクトップアプリの両方で直接インスタンス化できます。

Windows ランタイム C++ テンプレートライブラリを使用して従来の COM コンポーネントを作成し、外部デスクトップアプリからインスタンス化する方法については、「 [方法: 従来の Com コンポーネントを作成](how-to-create-a-classic-com-component-using-wrl.md)する」を参照してください。

このドキュメントでは、2 つの例を示します。 最初の例では、`Make` 関数を使用してコンポーネントをインスタンス化します。 2 番目の例では、`MakeAndInitialize` 関数を使用して構築中に失敗する場合があるコンポーネントをインスタンス化します  (COM は通常、例外ではなく HRESULT 値を使用してエラーを示すため、COM 型は通常、コンストラクターからスローされません。 `MakeAndInitialize` コンポーネントがメソッドを使用して構築引数を検証できるように `RuntimeClassInitialize` します。)どちらの例でも、基本的な logger インターフェイスを定義し、コンソールにメッセージを書き込むクラスを定義することでそのインターフェイスを実装します。

> [!IMPORTANT]
> 演算子を使用して `new` Windows ランタイム C++ テンプレートライブラリのコンポーネントをインスタンス化することはできません。 そのため、コンポーネントを直接インスタンス化するには、常に `Make` または `MakeAndInitialize` を使用することをお勧めします。

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>基本的なロガー コンポーネントを作成してインスタンス化するには

1. Visual Studio で、 **Win32 コンソールアプリケーション** プロジェクトを作成します。 プロジェクトに「 *Wrllogger*」などという名前を指定します。

2. **Midl ファイル (.idl)** ファイルをプロジェクトに追加し、ファイルに名前を指定して、次の `ILogger.idl` コードを追加します。

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. 次のコードを使用して、の内容を置き換え `WRLLogger.cpp` ます。

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>基本的なロガー コンポーネントの構造エラーを処理するには

1. 次のコードを使用して `CConsoleWriter` クラスの定義を置き換えます。 このバージョンは、プライベート文字列のメンバー変数を保持し、`RuntimeClass::RuntimeClassInitialize` メソッドをオーバーライドします。 `RuntimeClassInitialize` の呼び出しが失敗した場合に失敗 `SHStrDup` します。

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. 次のコードを使用して `wmain` の定義を置き換えます。 このバージョンでは、を使用して `MakeAndInitialize` オブジェクトをインスタンス化 `CConsoleWriter` し、HRESULT の結果をチェックします。

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft:: WRL:: Make](make-function.md)<br/>
[Microsoft:: WRL::D etails:: MakeAndInitialize](makeandinitialize-function.md)
