---
title: リンカー ツールの警告 LNK4049 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4049
dev_langs:
- C++
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b50dadc9c160ac8902cedcd60c954b565dce6e24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4049"></a>リンカー ツールの警告 LNK4049
ローカルに定義されたシンボル 'symbol' がインポート  
  
 シンボルが両方からエクスポートし、プログラムにインポートします。  
  
 使用してシンボルを宣言するときに、この警告がリンカーによって生成された、`__declspec(dllexport)`ストレージ クラス属性の 1 つのオブジェクト ファイルとを使用して参照、`__declspec(dllimport)`別の属性です。  
  
 警告 LNK4049 がより一般的なバージョンの[リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)です。 リンカーは、どの関数からインポートされたシンボルがへの参照を判断できないときに、警告 LNK4049 を生成します。  
  
 LNK4217 ではなく LNK4049 を生成する場所の一般的なケースは次のとおりです。  
  
-   使用してインクリメンタル リンクを実行する、 [/incremental](../../build/reference/incremental-link-incrementally.md)オプション。  
  
-   使用して、プログラム全体の最適化を実行する、 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)オプション。  
  
 LNK4049 を解決するには、次のいずれかを試してください。  
  
-   削除、 `__declspec(dllimport)` LNK4049 をトリガーするシンボルの事前宣言から宣言の名前を付けます。 使用してバイナリ イメージ内のシンボルを検索することができます、 **DUMPBIN**ユーティリティです。 **DUMPBIN/シンボル**スイッチには、イメージの COFF シンボル テーブルが表示されます。 詳細については、 **DUMPBIN**ユーティリティを参照してください[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)です。  
  
-   インクリメンタル リンクと、プログラム全体の最適化を一時的に無効にします。 アプリケーションを再コンパイルすると、インポートされたシンボルの参照元の関数の名前を含む警告 LNK4217 が生成されます。 削除、`__declspec(dllimport)`インポート シンボルとインクリメンタル リンクの有効化または必要に応じて、プログラム全体の最適化から宣言します。  
  
 最終的に生成されたコードが正しく動作は、インポートされた関数を呼び出すに生成されたコードは関数を直接呼び出すよりも効率が低下します。 オプションを使用してコンパイルするときに、この警告は表示されません[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
 詳細については、インポートし、データの宣言をエクスポートを参照してください。 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)です。  
  
## <a name="example"></a>例  
 次の 2 つのモジュールをリンクすると、LNK4049 が生成されます。 1 つ目のモジュールは、1 つのエクスポートされた関数を含むオブジェクト ファイルを生成します。  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## <a name="example"></a>例  
 2 番目のモジュール内でこの関数への呼び出しと共に、最初のモジュールでエクスポートされた関数に対する事前宣言を含むオブジェクト ファイルを生成する、`main`関数。 1 つ目のモジュールで、このモジュールをリンクすると、LNK4049 が生成されます。 削除、`__declspec(dllimport)`宣言は、警告を解決します。  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)