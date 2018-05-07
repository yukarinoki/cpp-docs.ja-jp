---
title: リンカ ツール エラー LNK1107 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fee2105cb0c12287cd2b47636f0e47011854a608
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1107"></a>リンカ ツール エラー LNK1107
ファイルが無効か破損しています: の場所で読み取ることができません  
  
 このツールは、ファイルを読み取れませんでした。 ファイルを再作成します。  
  
 モジュールを渡すしようとする場合にも LNK1107 (で作成された拡張子は .dll または .netmodule [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)または[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) リンカー; するには、.obj ファイルを代わりに渡します。  
  
 次の例: コンパイルする場合  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 指定し、 **LNK1107.dll をリンク**コマンド ラインで LNK1107 が表示されます。  エラーを解決するには、指定**リンク LNK1107.obj**代わりにします。