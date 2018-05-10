---
title: 使用するエクスポート方式の使い分け |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c88cee3504d8efef8f9ca19073ed06b66f6aeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="determining-which-exporting-method-to-use"></a>エクスポート方式の使い分け
2 つの方法のいずれかで関数をエクスポートすることができます: .def ファイルまたは`__declspec(dllexport)`キーワード。 DLL の向上方法を決定するために、これらの質問を考慮してください。  
  
-   後でより多くの関数をエクスポートする予定ですか。  
  
-   再構築できますが、使用したりできませんを再構築するアプリケーションでアプリケーションでのみ使用される DLL は、— たとえば、サード パーティによって作成されるアプリケーションですか?  
  
## <a name="pros-and-cons-of-using-def-files"></a>.Def ファイルを使用しての長所と短所  
 エクスポート序数を制御できる .def ファイルのための関数をエクスポートしています。 DLL にエクスポートされた関数を追加する場合は、他のエクスポートされた関数よりも高い序数値を割り当てることができます。 これを行うときに、暗黙的なリンクを使用するアプリケーションを新しい関数を含むインポート ライブラリとリンクし直すにはありません。 これは、新しい機能を追加しても既に依存するアプリケーションでは正しく動作を続行することを確認するので、多くのアプリケーションで使用するための DLL を設計する場合に非常に便利です。 たとえば、MFC Dll は、.def ファイルを使用して構築されます。  
  
 .Def ファイルを使用して、もう 1 つの利点は、使用できること、`NONAME`関数をエクスポートする属性。 これによって、DLL のエクスポート テーブルに序数だけです。 Dll の場合を使用して、エクスポートされた関数の数が多い、`NONAME`属性は、DLL ファイルのサイズを減らすことができます。 モジュール定義ステートメントを記述する方法については、次を参照してください。[モジュール定義ステートメントに関する規則](../build/reference/rules-for-module-definition-statements.md)です。 序数エクスポート方法については、次を参照してください。[関数名ではなく序数値に、DLL のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)です。  
  
 .Def ファイルを使用しての欠点は、またはするは、C++ ファイルで関数をエクスポートする場合、.def に装飾名を格納する必要があるいずれかのファイルに行われる名前の装飾を回避する extern"C"を使用して、エクスポートされた関数を定義する Visual C コンパイラでします。  
  
 使用して取得できる装飾名を .def ファイルに配置した場合は、 [DUMPBIN](../build/reference/dumpbin-reference.md)ツールまたはリンカーを使用して[/map](../build/reference/map-generate-mapfile.md)オプション。 コンパイラによって生成される装飾名はコンパイラ固有です。したがって、.def ファイルに、コンパイラによって生成される装飾名を配置した場合は、DLL にリンクするアプリケーションも構築する必要が呼び出し元のアプリケーション内の装飾名が、エクスポートされた一致するように同じバージョンのコンパイラを使用して i の名前n DLL の .def ファイルがあります。  
  
## <a name="pros-and-cons-of-using-declspecdllexport"></a>関数を使用しての長所と短所  
 使用して`__declspec(dllexport)`.def ファイルを管理して、エクスポートされた関数の装飾名の取得について心配する必要はありませんので便利です。 ただし、この方法でエクスポートの有用性を再構築してもよいリンクされたアプリケーションの数によって制限されます。 新しいエクスポートを含む DLL を再構築する場合は、再構築するさまざまなバージョンのコンパイラを使用する場合、エクスポートされた C++ 関数の装飾名は変わる可能性があるアプリケーションを再構築する必要があります。  
  
### <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [使用して、DLL からエクスポートします。DEF ファイル](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [インポートして、インライン関数をエクスポートします。](../build/importing-and-exporting-inline-functions.md)  
  
-   [相互インポート](../build/mutual-imports.md)  
  
-   [装飾名](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)