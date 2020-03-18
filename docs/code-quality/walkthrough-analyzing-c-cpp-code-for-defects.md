---
title: 'チュートリアル: C/C++コード分析による欠陥の分析'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: 5fbdf9e223b3c1e1b8664de2018381958c458f45
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2020
ms.locfileid: "79467067"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>チュートリアル: C/C++コード分析による欠陥の分析

このチュートリアルでは、C/C++ C++ code 用のコード分析ツールを使用して、コードの欠陥の可能性について c/コードを分析する方法について説明します。

- ネイティブコードでコード分析を実行します。
- コード障害の警告を分析します。
- 警告をエラーとして扱います。
- コード障害分析を改善するためにソースコードに注釈を付けます。

## <a name="prerequisites"></a>前提条件

- [デモサンプル](../code-quality/demo-sample.md)のコピー。
- C/C++の基本を理解している。

### <a name="to-run-code-defect-analysis-on-native-code"></a>ネイティブコードでコードの欠陥分析を実行するには

1. Visual Studio でデモソリューションを開きます。

     デモソリューションで**ソリューションエクスプローラー**が設定されるようになりました。

1. **[ビルド]** メニューで、 **[ソリューションのリビルド]** をクリックします。

     エラーや警告なしでソリューションがビルドされます。

1. **ソリューションエクスプローラー**で、codedefects プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     **[Codedefects プロパティページ]** ダイアログボックスが表示されます。

1. **[コード分析]** をクリックします。

1. **[C/C++ビルド時にコード分析を有効にする]** チェックボックスをオンにします。

1. CodeDefects プロジェクトをリビルドします。

     コード分析の警告が**エラー一覧**に表示されます。

### <a name="to-analyze-code-defect-warnings"></a>コード障害の警告を分析するには

1. **[表示]** メニューの **[エラー一覧]** をクリックします。

     Visual Studio で選択した開発者プロファイルによっては、 **[表示]** メニューの **[その他のウィンドウ]** をポイントし、 **[エラー一覧]** をクリックすることが必要になる場合があります。

1. **エラー一覧**で、次の警告をダブルクリックします。

     警告 C6230: 意味の異なる型の間の暗黙的なキャストです: ブール値のコンテキストで HRESULT を使用しています。

     コードエディターでは、関数 `bool ProcessDomain()`で警告の原因となった行が表示されます。 この警告は、ブール型の結果が想定される ' if ' ステートメントで `HRESULT` が使用されていることを示します。  これは通常、`S_OK` HRESULT がその関数から返された場合は成功を示していますが、ブール値に変換されると `false`に評価されるため、これは誤りです。

1. `SUCCEEDED` マクロを使用してこの警告を修正します。このマクロは、`HRESULT` の戻り値が成功を示す場合に `true` に変換します。 コードは次のコードのようになります。

   ```cpp
   if (SUCCEEDED (ReadUserAccount()) )
   ```

1. **エラー一覧**で、次の警告をダブルクリックします。

     警告 C6282: 不適切な演算子です: テストコンテキストで定数に割り当てられています。 Was = = 意図されていますか?

1. 等しいかどうかをテストして、この警告を修正します。 コードは次のコードのようになります。

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))
   ```

### <a name="to-treat-warning-as-an-error"></a>警告をエラーとして扱うには

1. バグの .cpp ファイルで、次の `#pragma` ステートメントをファイルの先頭に追加し、警告 C6001 をエラーとして扱います。

   ```cpp
   #pragma warning (error: 6001)
   ```

1. CodeDefects プロジェクトをリビルドします。

     **エラー一覧**では、C6001 がエラーとして表示されるようになりました。

1. `i` を初期化し、を0に `j` して、**エラー一覧**の残りの2つの C6001 エラーを修正します。

1. CodeDefects プロジェクトをリビルドします。

     プロジェクトがビルドされ、警告やエラーは発生しません。

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>注釈のソースコードの注釈の警告を修正するには

1. ソリューションエクスプローラーで、[注釈] プロジェクトを選択します。

1. **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

     **[注釈のプロパティページ]** ダイアログボックスが表示されます。

1. **[コード分析]** をクリックします。

1. **[C/C++ビルド時にコード分析を有効にする]** チェックボックスをオンにします。

1. Annotations プロジェクトをリビルドします。

1. **エラー一覧**で、次の警告をダブルクリックします。

     警告 C6011: NULL ポインター ' newNode ' を逆参照しています。

     この警告は、呼び出し元が戻り値を確認するのに失敗したことを示します。 この場合、 **allocatenode**呼び出しによって NULL 値が返される可能性があります (allocatenode 関数宣言については、「annotations ヘッダーファイル」を参照してください)。

1. Annotations ファイルを開きます。

1. この警告を解決するには、' if ' ステートメントを使用して戻り値をテストします。 コードは次のコードのようになります。

   ```cpp
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. Annotations プロジェクトをリビルドします。

     プロジェクトがビルドされ、警告やエラーは発生しません。

### <a name="to-use-source-code-annotation"></a>ソースコードの注釈を使用するには

1. ポインター値が null であることを示すために、関数 `AddTail` の仮パラメーターと戻り値に注釈を設定します。

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. コメントプロジェクトを再構築します。

1. **エラー一覧**で、次の警告をダブルクリックします。

     警告 C6011: NULL ポインター ' node ' を逆参照しています。

     この警告は、関数に渡されたノードが null である可能性があることを示し、警告が発生した行番号を示します。

1. この警告を解決するには、関数の先頭にある ' if ' ステートメントを使用して、渡された値をテストします。 コードは次のコードのようになります。

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. コメントプロジェクトを再構築します。

     プロジェクトは、警告やエラーなしでビルドされるようになりました。

## <a name="see-also"></a>参照

[チュートリアル: マネージコードの分析によるコード障害の](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/のコード分析C++](../code-quality/code-analysis-for-c-cpp-overview.md)
