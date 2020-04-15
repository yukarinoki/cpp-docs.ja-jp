---
title: 'チュートリアル: C/C++ コードの欠陥の分析'
description: コード分析を Visual Studio で Microsoft C++ で使用する方法を示します。
ms.date: 04/14/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: fe9b3775199b2a18cf940b99e87852350f1fbea9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370209"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>チュートリアル: C/C++ コードの欠陥の分析

このチュートリアルでは、C/C++ コードを分析して、潜在的なコードの欠陥を分析する方法を示します。 C/C++ コードのコード分析ツールを使用します。

このチュートリアルでは、次の手順を実行します。

- ネイティブ コードでコード分析を実行します。
- コードの不具合の警告を分析します。
- 警告をエラーとして扱います。
- ソース コードにアコージンケートを行い、コード不良分析を改善します。

## <a name="prerequisites"></a>前提条件

- [CppDemo サンプル](../code-quality/demo-sample.md)のコピー。
- C/C++ の基本知識。

## <a name="run-code-analysis-on-native-code"></a>ネイティブ コードでコード分析を実行する

### <a name="to-run-code-defect-analysis-on-native-code"></a>ネイティブ コードでコードの欠陥分析を実行するには

::: moniker range=">=vs-2019"

1. CppDemo ソリューションを開きます。

     CppDemo ソリューションがソリューション**エクスプローラ**にデータを読み込むようになりました。

1. [**ビルド**] メニューの [**ソリューションの再構築**] をクリックします。

     ソリューションは、エラーや警告なしでビルドされます。

1. **ソリューション エクスプローラー**で、CodeDefects プロジェクトを選択します。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。

     **[CodeDefects プロパティ ページ**] ダイアログ ボックスが表示されます。

1. [**コード分析**] プロパティ ページを選択します。

1. [**ビルド時にコード分析を有効にする]** プロパティを **[はい**] に変更します。 **[OK]** を選択して変更を保存します。

1. コードの問題プロジェクトを再構築します。

     コード分析の警告は、[**エラー一覧**] ウィンドウに表示されます。

::: moniker-end

::: moniker range="<=vs-2017"

1. CppDemo ソリューションを開きます。

     CppDemo ソリューションがソリューション**エクスプローラ**にデータを読み込むようになりました。

1. [**ビルド**] メニューの [**ソリューションの再構築**] をクリックします。

     ソリューションは、エラーや警告なしでビルドされます。

     > [!NOTE]
     > Visual Studio 2017 では、IntelliSense`E1097 unknown attribute "no_init_all"`エンジンにスプリアス警告が表示される場合があります。 この警告は無視してかまいません。

1. **ソリューション エクスプローラー**で、CodeDefects プロジェクトを選択します。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。

     **[CodeDefects プロパティ ページ**] ダイアログ ボックスが表示されます。

1. [**コード分析**] プロパティ ページを選択します。

1. [**ビルド時にコード分析を有効にする**] チェック ボックスをオンにします。 **[OK]** を選択して変更を保存します。

1. コードの問題プロジェクトを再構築します。

     コード分析の警告は、[**エラー一覧**] ウィンドウに表示されます。

::: moniker-end

### <a name="to-analyze-code-defect-warnings"></a>コードの欠陥の警告を分析するには

1. [**表示**] メニューの [**エラー一覧**] をクリックします。

     このメニュー項目は表示されない可能性があります。 これは、Visual Studio で選択した開発者プロファイルによって異なります。 [**表示**] メニュー**の [その他のウィンドウ**] をポイントし、[**エラー一覧**] をクリックする必要がある場合があります。

1. [**エラー一覧**] ウィンドウで、次の警告をダブルクリックします。

     C6230: 意味的に異なる型間の暗黙的なキャスト: ブールコンテキストで HRESULT を使用します。

     コード エディターには、関数`bool ProcessDomain()`内で警告が発生した行が表示されます。 この警告は、ブール`HRESULT`演算結果が予想される 'if' ステートメントで a が使用されていることを示します。 `S_OK`通常は、関数から HRESULT が返されると成功を示しますが、ブール値に変換すると評価されるため、通常は間違いです`false`。

1. この警告を修正するには、`SUCCEEDED`戻り値が成功を`true`示す`HRESULT`場合に変換するマクロを使用します。 コードは次のコードのようになります。

   ```cpp
   if (SUCCEEDED(ReadUserAccount()))
   ```

1. [**エラー一覧**] で、次の警告をダブルクリックします。

     C6282: 演算子が正しくありません: ブール演算コンテキストで定数を割り当てています。 代わりに '==' を使用することを検討してください。

1. この警告を修正して、等しいかどうかテストします。 コードは次のようになります。

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
   ```

1. 0 を初期化`i`して **、エラー一覧**の残りの C6001 警告`j`を修正します。

1. コードの問題プロジェクトを再構築します。

     プロジェクトは、警告やエラーなしでビルドされます。

## <a name="correct-source-code-annotation-warnings"></a>ソース コードアノテーションの警告を修正する

### <a name="to-enable-the-source-code-annotation-warnings-in-annotationc"></a>注釈でソース コードアノテーションの警告を有効にするには

::: moniker range=">=vs-2019"

1. ソリューション エクスプローラーで、注釈プロジェクトを選択します。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。

     [**注釈プロパティ ページ]** ダイアログ ボックスが表示されます。

1. [**コード分析**] プロパティ ページを選択します。

1. [**ビルド時にコード分析を有効にする]** プロパティを **[はい**] に変更します。 **[OK]** を選択して変更を保存します。

::: moniker-end

::: moniker range="<=vs-2017"

1. ソリューション エクスプローラーで、注釈プロジェクトを選択します。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。

     [**注釈プロパティ ページ]** ダイアログ ボックスが表示されます。

1. [**コード分析**] プロパティ ページを選択します。

1. [**ビルド時にコード分析を有効にする**] チェック ボックスをオンにします。 **[OK]** を選択して変更を保存します。

::: moniker-end

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>注釈でソース コードアノテーションの警告を修正するには

1. 注釈プロジェクトを再構築します。

1. [**ビルド**] メニューの [**注釈に対するコード分析の実行**] をクリックします。

1. [**エラー一覧**] で、次の警告をダブルクリックします。

     C6011: NULL ポインタ 'newNode' を逆参照します。

     この警告は、呼び出し元が戻り値をチェックできなかったことを示します。 この場合、呼`AllocateNode`び出しは NULL 値を返す可能性があります。 の関数宣言については、annotations.h ヘッダー ファイル`AllocateNode`を参照してください。

1. カーソルは、警告が発生した annotations.cpp ファイル内の位置にあります。

1. この警告を修正するには、'if' ステートメントを使用して戻り値をテストします。 コードは次のコードのようになります。

   ```cpp
   LinkedList* newNode = AllocateNode();
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. 注釈プロジェクトを再構築します。

     プロジェクトは、警告やエラーなしでビルドされます。

## <a name="use-source-code-annotation-to-discover-more-issues"></a>ソース コードアノテーションを使用して、より多くの問題を発見する

### <a name="to-use-source-code-annotation"></a>ソース コードアノテーションを使用するには

1. ポインタ値を示`AddTail`す関数の仮パラメータと戻り値に対して、次の値が null である可能性があります。

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. [**ビルド**] メニューの [**ソリューションでコード分析を実行**] をクリックします。

1. [**エラー一覧**] で、次の警告をダブルクリックします。

     C6011: NULL ポインタ 'ノード' を逆参照しています。

     この警告は、関数に渡されたノードが null である可能性があることを示します。

1. この警告を修正するには、関数の先頭で 'if' ステートメントを使用して、渡された値をテストします。 コードは次のコードのようになります。

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. [**ビルド**] メニューの [**ソリューションでコード分析を実行**] をクリックします。

     プロジェクトは、警告やエラーなしでビルドされるようになりました。

## <a name="see-also"></a>関連項目

[チュートリアル : コードの欠陥に対するマネージ コードの分析](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/C++ のコード分析](../code-quality/code-analysis-for-c-cpp-overview.md)
