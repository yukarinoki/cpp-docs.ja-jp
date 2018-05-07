---
title: リンカ ツール エラー LNK1561 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8de3a8eebb8cc023f3ee6f2d2e4c82e718fe79e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1561"></a>リンカ ツール エラー LNK1561
エントリ ポイントを定義する必要があります。  
  
リンカーが見つかりませんでした、*エントリ ポイント*、実行可能ファイルでの呼び出しに初期関数。 既定では、リンカー検索、`main`または`wmain`コンソール アプリの関数、`WinMain`または`wWinMain`for Windows アプリでは、関数または`DllMain`dll の初期化が必要です。 別の関数を使用して指定することができます、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
  
このエラーは、いくつかの原因を持つことができます。  
-   リンクするファイルの一覧で、エントリ ポイントを定義するファイルが含まれていない可能性があります。 エントリ ポイント関数を格納しているファイルがアプリにリンクされていることを確認します。  
-   間違った関数のシグネチャ; を使用して、エントリ ポイントを定義した可能性があります。たとえば、する可能性がありますがスペルが間違っているまたは関数名が大文字を使用または正しく指定されていない戻り値の型またはパラメーターの型。  
-   指定していない、 [/DLL](../../build/reference/dll-build-a-dll.md) DLL のビルド オプションを選択します。  
-   場合がありますが正しく指定されていないエントリ ポイント関数の名前を使用した場合、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
-   使用している場合、 [LIB](../../build/reference/lib-reference.md) DLL をビルドするツール、.def ファイルを指定した可能性があります。 場合は、ビルドから、.def ファイルを削除します。    
  
アプリを構築するには、リンカーは、コードを開始するために呼び出すエントリ ポイント関数が検索されます。 これは、アプリが読み込まれ、ランタイムを初期化後に呼び出される関数です。 アプリケーションのためのエントリ ポイント関数を指定する必要がありますか、アプリを実行できません。 エントリ ポイントは、DLL のオプションです。 既定では、リンカー検索など、いくつかの特定の名前とシグネチャのいずれかのエントリ ポイント関数`int main(int, char**)`です。 エントリとして別の関数名を指定できます/ENTRY リンカー オプションを使用してポイント。  
  
## <a name="example"></a>例  
 次の例では、LNK1561 が生成されます。  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```