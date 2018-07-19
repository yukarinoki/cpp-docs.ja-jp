---
title: 'チュートリアル: 標準の C++ プログラム (C++) の作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: ac1fac3c7f96c9f8d718efa54810f4155b1ddac5
ms.sourcegitcommit: c0ffdff538eb961f786809eb547b35846190ee48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34800087"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>チュートリアル: 標準の C++ プログラム (C++) の作成
Visual Studio の Visual C++ の統合開発環境 (IDE: Integrated Development Environment) を使用して、標準 C++ プログラムを作成できます。 このチュートリアルの手順に従って、プロジェクトを作成し、プロジェクトに新しいファイルを追加してから、ファイルを変更して C++ コードを追加できます。次に、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] を使用してプログラムをコンパイルし、実行できます。  
  
 独自の C++ プログラムを入力するか、サンプル プログラムを使用できます。 このチュートリアルのサンプル プログラムは、コンソール アプリケーションです。 このアプリケーションを使用して、 `set` C++ 標準ライブラリ内のコンテナーです。  
  
 Visual C がこれらの主要な例外を除き、2003 C++ 標準に準拠しています。 2 段階名前検索、例外の指定、およびエクスポートします。 さらに、Visual C には、たとえば、ラムダ、auto、static_assert、rvalue 参照、および extern テンプレートのいくつかの c++ 0 x 機能がサポートしています。  
  
> [!NOTE]
>  標準への遵守が必要な場合は、使用、 **/Za**コンパイラ オプションで、標準に対する Microsoft 拡張機能を無効にします。 詳細については、次を参照してください。 [/Za、/Ze (言語拡張を無効にする)](../build/reference/za-ze-disable-language-extensions.md)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するには、C++ 言語の基本を理解している必要があります。  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>プロジェクトを作成してソース ファイルを追加するには  
  
1.  指すことによって、プロジェクトを作成する**新規**上、**ファイル**メニューをクリックし、**プロジェクト**です。  
  
2.  **Visual C**プロジェクトの種類 ペインでをクリックして**Windows デスクトップ**、クリックして**Windows コンソール アプリケーション**です。  
  
3.  プロジェクトの名前を入力します。  
  
     既定では、プロジェクトを含むソリューションはプロジェクトと同じ名前になりますが、別の名前を入力してもかまいません。 プロジェクトの場所として別の場所を入力することもできます。  
  
     **[OK]** をクリックして、プロジェクトを作成します。  
  
4.  場合**ソリューション エクスプ ローラー**が表示されない、**ビュー**  メニューのをクリックして**ソリューション エクスプ ローラー**です。  
  
5.  次のように、プロジェクトに新しいソース ファイルを追加します。  
  
    1.  **ソリューション エクスプ ローラー**を右クリックし、**ソース ファイル**フォルダーを指す**追加**、順にクリック**新しい項目の**します。  
  
    2.  **コード** ノードをクリックして**C++ ファイル (.cpp)**、ファイルの名前を入力して、をクリックして**追加**です。  
  
     [ソース ファイル] フォルダーに .cpp ファイルが表示**ソリューション エクスプ ローラー**、され、ファイルが Visual Studio エディターで開かれます。  
  
6.  ファイルがエディターで、C++ 標準ライブラリを使用する有効な C++ プログラムを入力またはサンプル プログラムの 1 つをコピーで、ファイルに貼り付けます。  
  
7.  ファイルを保存します。  
  
8. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **出力**ウィンドウには、コンパイルの進行状況、ビルド ログおよびビルドの状態を示すメッセージの場所などに関する情報が表示されます。  
  
9. **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
     サンプル プログラムを使用した場合、コマンド ウィンドウが表示され、コマンドセット内に特定の整数があるかどうかが示されます。  
  
## <a name="next-steps"></a>次の手順  
 **前:** [Visual C のアプリケーションをコンソール](../windows/console-applications-in-visual-cpp.md)です。 **次へ:**[チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
