---
title: 'チュートリアル: 標準の C++ プログラム (C++) の作成 |Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff4a2078bef03127507d1da35599ea391904bee7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382636"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>チュートリアル: 標準の C++ プログラム (C++) の作成

Visual Studio の Visual C++ の統合開発環境 (IDE: Integrated Development Environment) を使用して、標準 C++ プログラムを作成できます。 手順に従って、このチュートリアルでは、プロジェクトを作成する、プロジェクトに新しいファイルを追加、C++ コードを追加して、コンパイルし、Visual Studio を使用して、プログラムを実行するファイルを変更することができます。

独自の C++ プログラムを入力するか、サンプル プログラムを使用できます。 このチュートリアルのサンプル プログラムは、コンソール アプリケーションです。 このアプリケーションを使用して、 `set` C++ 標準ライブラリ内のコンテナー。

Visual C がこれらの主な例外を除き、2003 C++ 標準に準拠している。 2 段階名前検索、例外の仕様、およびエクスポートします。 さらに、Visual C では、いくつかの c++ 0 x 機能、たとえば、ラムダ、auto、static_assert、rvalue 参照、および extern テンプレートをサポートしています。

> [!NOTE]
> 標準への準拠が必要な場合は、`/Za` コンパイラ オプションを使用して、標準に対する Microsoft 拡張機能を無効にします。 詳細については、次を参照してください。 [/Za、/Ze (言語拡張を無効にする)](../build/reference/za-ze-disable-language-extensions.md)します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、C++ 言語の基本を理解している必要があります。

### <a name="to-create-a-project-and-add-a-source-file"></a>プロジェクトを作成してソース ファイルを追加するには

1. をポイントしてプロジェクトを作成**新規**上、**ファイル** メニューのをクリックして**プロジェクト**します。

2. **Visual C**プロジェクトの種類ウィンドウで、をクリックして**Windows デスクトップ**、 をクリックし、 **Windows コンソール アプリケーション**します。

3. プロジェクトの名前を入力します。

   既定では、プロジェクトを含むソリューションはプロジェクトと同じ名前になりますが、別の名前を入力してもかまいません。 プロジェクトの場所として別の場所を入力することもできます。

   **[OK]** をクリックして、プロジェクトを作成します。

4. 場合**ソリューション エクスプ ローラー**が表示されない、**ビュー**  メニューのをクリックして**ソリューション エクスプ ローラー**します。

5. 次のように、プロジェクトに新しいソース ファイルを追加します。

   1. **ソリューション エクスプ ローラー**を右クリックし、**ソース ファイル**フォルダーを指す**追加**、順にクリックします**新しい項目の**します。

   2. **コード**ノード、をクリックして**C++ ファイル (.cpp)**、ファイルの名前を入力し、クリックして**追加**します。

   .Cpp ファイルに表示されます、**ソース ファイル**フォルダー**ソリューション エクスプ ローラー**、Visual Studio エディターでファイルを開くとします。

6. エディターでファイルに、C++ 標準ライブラリを使用する有効な C++ プログラムを入力またはサンプル プログラムの 1 つのコピーし、ファイルに貼り付けます。

7. ファイルを保存します。

8. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   **出力**ウィンドウは、コンパイルの進行状況、ビルド ログとビルドの状態を示すメッセージの場所などに関する情報を表示します。

9. **[デバッグ]** メニューの **[デバッグなしで開始]** をクリックします。

   サンプル プログラムを使用した場合、コマンド ウィンドウが表示され、コマンドセット内に特定の整数があるかどうかが示されます。

## <a name="next-steps"></a>次の手順

**前:** [コンソール アプリケーション Visual C で](../windows/console-applications-in-visual-cpp.md)します。 **次:**[チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)します。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)