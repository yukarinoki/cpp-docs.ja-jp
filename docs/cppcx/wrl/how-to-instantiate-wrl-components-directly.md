---
title: '方法: WRL コンポーネントを直接インスタンス化する'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: f291e982d7f77c63821e5943a5867662ccd1b4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213903"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>方法: WRL コンポーネントを直接インスタンス化する

Windows ランタイムC++テンプレートライブラリ (wrl)[microsoft:: Wrl:: Make](make-function.md)および[microsoft:: wrl::D Etails:: makeandinitialize](makeandinitialize-function.md)関数を使用して、コンポーネントを定義するモジュールからコンポーネントをインスタンス化する方法について説明します。

コンポーネントを直接インスタンス化することにより、クラス ファクトリやその他の機構が必要ない場合にオーバーヘッドを低減できます。 コンポーネントは、ユニバーサル Windows プラットフォームアプリとデスクトップアプリの両方で直接インスタンス化できます。

Windows ランタイムC++テンプレートライブラリを使用して従来の com コンポーネントを作成し、外部のデスクトップアプリからインスタンス化する方法については、「[方法: 従来の Com コンポーネントを作成](how-to-create-a-classic-com-component-using-wrl.md)する」を参照してください。

このドキュメントでは、2 つの例を示します。 最初の例では、`Make` 関数を使用してコンポーネントをインスタンス化します。 2 番目の例では、`MakeAndInitialize` 関数を使用して構築中に失敗する場合があるコンポーネントをインスタンス化します (COM は通常、例外ではなく HRESULT 値を使用してエラーを示すため、COM 型は通常、コンストラクターからスローされません。 `MakeAndInitialize` を使用すると、コンポーネントは、`RuntimeClassInitialize` メソッドを使用して構築引数を検証できます)。どちらの例でも、基本的な logger インターフェイスを定義し、コンソールにメッセージを書き込むクラスを定義することでそのインターフェイスを実装します。

> [!IMPORTANT]
> `new` 演算子を使用して、Windows ランタイムC++テンプレートライブラリコンポーネントをインスタンス化することはできません。 そのため、コンポーネントを直接インスタンス化するには、常に `Make` または `MakeAndInitialize` を使用することをお勧めします。

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>基本的なロガー コンポーネントを作成してインスタンス化するには

1. Visual Studio で、 **Win32 コンソールアプリケーション**プロジェクトを作成します。 プロジェクトに「 *Wrllogger*」などという名前を指定します。

2. **Midl ファイル (.idl)** ファイルをプロジェクトに追加し、ファイルに `ILogger.idl`という名前を指定して、次のコードを追加します。

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. 次のコードを使用して、`WRLLogger.cpp`の内容を置き換えます。

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>基本的なロガー コンポーネントの構造エラーを処理するには

1. 次のコードを使用して `CConsoleWriter` クラスの定義を置き換えます。 このバージョンは、プライベート文字列のメンバー変数を保持し、`RuntimeClass::RuntimeClassInitialize` メソッドをオーバーライドします。 `SHStrDup` への呼び出しが失敗した場合、`RuntimeClassInitialize` は失敗します。

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. 次のコードを使用して `wmain` の定義を置き換えます。 このバージョンでは、`MakeAndInitialize` を使用して `CConsoleWriter` オブジェクトをインスタンス化し、HRESULT の結果を確認します。

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>参照

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft:: WRL:: Make](make-function.md)<br/>
[Microsoft:: WRL::D etails:: MakeAndInitialize](makeandinitialize-function.md)
