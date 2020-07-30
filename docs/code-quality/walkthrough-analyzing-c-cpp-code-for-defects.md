---
title: 'チュートリアル: C/c + + コード分析による欠陥の分析'
description: Visual Studio で Microsoft C++ でコード分析を使用する方法について説明します。
ms.date: 04/14/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: 65da18f5f6d1972276f1cb8e306e82314282e40a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227713"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>チュートリアル: C/c + + コード分析による欠陥の分析

このチュートリアルでは、C/c + + コードを分析して、潜在的なコード障害を把握する方法について説明します。 C/c + + コードのコード分析ツールを使用します。

このチュートリアルでは、次のことについて説明します。

- ネイティブコードでコード分析を実行します。
- コード障害の警告を分析します。
- 警告をエラーとして扱います。
- コード障害分析を改善するためにソースコードに注釈を付けます。

## <a name="prerequisites"></a>前提条件

- [Cppdemo サンプル](../code-quality/demo-sample.md)のコピー。
- C/c + + に関する基本的な知識。

## <a name="run-code-analysis-on-native-code"></a>ネイティブコードでコード分析を実行する

### <a name="to-run-code-defect-analysis-on-native-code"></a>ネイティブコードでコードの欠陥分析を実行するには

::: moniker range=">=vs-2019"

1. Visual Studio で CppDemo ソリューションを開きます。

     CppDemo ソリューションが**ソリューションエクスプローラー**に設定されるようになりました。

1. [**ビルド**] メニューの [**ソリューションのリビルド**] をクリックします。

     エラーや警告なしでソリューションがビルドされます。

1. [**ソリューションエクスプローラー**で、[codedefects] プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     [ **Codedefects プロパティページ**] ダイアログボックスが表示されます。

1. [**コード分析**] プロパティページを選択します。

1. [**ビルドのコード分析を有効**にする **] プロパティを [はい]** に変更します。 **[OK]** を選択して変更を保存します。

1. CodeDefects プロジェクトをリビルドします。

     コード分析の警告は、[**エラー一覧**] ウィンドウに表示されます。

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio で CppDemo ソリューションを開きます。

     CppDemo ソリューションが**ソリューションエクスプローラー**に設定されるようになりました。

1. [**ビルド**] メニューの [**ソリューションのリビルド**] をクリックします。

     エラーや警告なしでソリューションがビルドされます。

     > [!NOTE]
     > Visual Studio 2017 では、IntelliSense エンジンに誤った警告が表示されることがあり `E1097 unknown attribute "no_init_all"` ます。 この警告は無視してかまいません。

1. [**ソリューションエクスプローラー**で、[codedefects] プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     [ **Codedefects プロパティページ**] ダイアログボックスが表示されます。

1. [**コード分析**] プロパティページを選択します。

1. [**ビルド時にコード分析を有効にする**] チェックボックスをオンにします。 **[OK]** を選択して変更を保存します。

1. CodeDefects プロジェクトをリビルドします。

     コード分析の警告は、[**エラー一覧**] ウィンドウに表示されます。

::: moniker-end

### <a name="to-analyze-code-defect-warnings"></a>コード障害の警告を分析するには

1. [**表示**] メニューの [**エラー一覧**] をクリックします。

     このメニュー項目は、表示されない可能性があります。 これは、Visual Studio で選択した開発者プロファイルによって異なります。 [**表示**] メニューの [**その他のウィンドウ**] をポイントし、[**エラー一覧**] を選択する必要がある場合があります。

1. [**エラー一覧**] ウィンドウで、次の警告をダブルクリックします。

     C6230: 意味の異なる型の間の暗黙的なキャストです。ブール値のコンテキストで HRESULT を使用しています。

     コードエディターでは、関数内で警告が発生した行が表示され `bool ProcessDomain()` ます。 この警告は、 `HRESULT` ブール型の結果が想定される ' if ' ステートメントでが使用されていることを示します。 通常は間違ってい `S_OK` ます。 HRESULT が関数から返された場合は成功を示しますが、ブール値に変換されるとに評価され **`false`** ます。

1. マクロを使用してこの警告を修正 `SUCCEEDED` **`true`** します。これは、戻り値が成功を示す場合にに変換され `HRESULT` ます。 コードは次のコードのようになります。

   ```cpp
   if (SUCCEEDED(ReadUserAccount()))
   ```

1. **エラー一覧**で、次の警告をダブルクリックします。

     C6282: 不適切な演算子です: ブール値のコンテキストで定数が割り当てられています。 代わりに ' = = ' を使用することを検討してください。

1. 等しいかどうかをテストして、この警告を修正します。 コードは次のコードのようになります。

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
   ```

1. とを0に初期化して、**エラー一覧**の残りの C6001 警告を修正し `i` `j` ます。

1. CodeDefects プロジェクトをリビルドします。

     プロジェクトがビルドされ、警告やエラーは発生しません。

## <a name="correct-source-code-annotation-warnings"></a>正しいソースコードの注釈の警告

### <a name="to-enable-the-source-code-annotation-warnings-in-annotationc"></a>Annotation でソースコードの注釈の警告を有効にするには

::: moniker range=">=vs-2019"

1. ソリューションエクスプローラーで、[注釈] プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     [**注釈のプロパティページ**] ダイアログボックスが表示されます。

1. [**コード分析**] プロパティページを選択します。

1. [**ビルドのコード分析を有効**にする **] プロパティを [はい]** に変更します。 **[OK]** を選択して変更を保存します。

::: moniker-end

::: moniker range="<=vs-2017"

1. ソリューションエクスプローラーで、[注釈] プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     [**注釈のプロパティページ**] ダイアログボックスが表示されます。

1. [**コード分析**] プロパティページを選択します。

1. [**ビルド時にコード分析を有効にする**] チェックボックスをオンにします。 **[OK]** を選択して変更を保存します。

::: moniker-end

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>注釈のソースコードの注釈の警告を修正するには

1. Annotations プロジェクトをリビルドします。

1. [**ビルド**] メニューの [**注釈に対してコード分析を実行**] をクリックします。

1. **エラー一覧**で、次の警告をダブルクリックします。

     C6011: NULL ポインター ' newNode ' を逆参照しています。

     この警告は、呼び出し元が戻り値を確認するのに失敗したことを示します。 この場合、を呼び出すと、 `AllocateNode` NULL 値が返される可能性があります。 の関数宣言については、annotations ヘッダーファイルを参照して `AllocateNode` ください。

1. カーソルは、警告が発生した、注釈 .cpp ファイル内の場所にあります。

1. この警告を解決するには、' if ' ステートメントを使用して戻り値をテストします。 コードは次のコードのようになります。

   ```cpp
   LinkedList* newNode = AllocateNode();
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. Annotations プロジェクトをリビルドします。

     プロジェクトがビルドされ、警告やエラーは発生しません。

## <a name="use-source-code-annotation-to-discover-more-issues"></a>ソースコード注釈を使用してさらに問題を検出する

### <a name="to-use-source-code-annotation"></a>ソースコードの注釈を使用するには

1. ポインター値が null であることを示すために、仮パラメーターと関数の戻り値 `AddTail` に注釈を設定します。

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. [**ビルド**] メニューの [**ソリューションでコード分析を実行**] をクリックします。

1. **エラー一覧**で、次の警告をダブルクリックします。

     C6011: NULL ポインター ' node ' を逆参照しています。

     この警告は、関数に渡されたノードが null である可能性があることを示します。

1. この警告を解決するには、関数の先頭にある ' if ' ステートメントを使用して、渡された値をテストします。 コードは次のコードのようになります。

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. [**ビルド**] メニューの [**ソリューションでコード分析を実行**] をクリックします。

     プロジェクトは、警告やエラーなしでビルドされるようになりました。

## <a name="see-also"></a>関連項目

[チュートリアル: マネージコードの分析によるコード障害の分析](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/C++ のコード分析](../code-quality/code-analysis-for-c-cpp-overview.md)
