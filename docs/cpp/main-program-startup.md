---
title: 'main: プログラムの起動 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f78a122837fc2cb9a89083d5be8fd2b488c1772
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939225"
---
# <a name="main-program-startup"></a>main: プログラムの起動
という名前の特殊な関数`main`はすべての C および C++ プログラムの実行の開始ポイントです。 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] プログラミング モデルに準拠するコードを書く場合は、`wmain` のワイド文字バージョンである `main` を使用できます。  
  
 `main` 関数は、コンパイラによってあらかじめ定義されていません。 これは、プログラム テキストに記述する必要があります。  
  
 `main` の宣言構文は次のとおりです。  
  
```cpp 
int main();  
```  
  
 または、必要に応じて次のように記述します。  
  
```cpp 
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様 →  
 `wmain` の宣言構文は次のとおりです。  
  
```cpp 
int wmain( );  
```  
  
 または、必要に応じて次のように記述します。  
  
```cpp 
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 TCHAR.h で定義されている `_tmain` を使用することもできます。 _UNICODE が定義されていない場合、`_tmain` は `main` に解決されます。 定義されている場合、`_tmain` は `wmain` に解決されます。  
  
 または、`main`と`wmain`返すように関数を宣言できます**void** (戻り値はありません)。 宣言する場合`main`または`wmain`返すよう**void**を使用して、親プロセスまたはオペレーティング システムに終了コードを返すことはできません、[返す](../cpp/return-statement-in-program-termination-cpp.md)ステートメント。 返される、ときに終了コード`main`または`wmain`として宣言されている**void**、使用する必要があります、[終了](../cpp/exit-function.md)関数。  
  
**Microsoft 固有の仕様はここまで**  
 `argc` と `argv` の型は、言語によって定義されています。 名前 `argc`、`argv`、および`envp` は従来のものですが、コンパイラにとって必須ではありません。 詳細と例では、次を参照してください。[引数定義](../cpp/argument-definitions.md)します。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [Main に代わる wmain の使用](../cpp/using-wmain-instead-of-main.md)   
 [main 関数に関する制約](../cpp/main-function-restrictions.md)   
 [C++ コマンド ライン引数の解析](../cpp/parsing-cpp-command-line-arguments.md)
