---
title: _Declspec (dllimport) を使用して関数呼び出しのインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1239ee3b33a9d6c8443161bacae6daea20260c1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368536"
---
# <a name="importing-function-calls-using-declspecdllimport"></a>__declspec(dllimport) を使った関数呼び出しのインポート
次のコード例は、使用する方法を示しています。 **_declspec(dllimport)** DLL から関数の呼び出しをアプリケーションにインポートします。 あると想定`func1`関数を含む .exe ファイルとは別の DLL に存在するは、**メイン**関数。  
  
 せず **_declspec**、このコードを指定します。  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 コンパイラでは、次のようなコードが生成されます。  
  
```  
call func1  
```  
  
 リンカーは、次のように呼び出しを変換します。  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 場合`func1`に存在する別の DLL、リンカーがこの直接解決できないのアドレスを知ることがあるないため`func1`はします。 16 ビット環境では、リンカーは、ローダーは実行時に、適切なアドレスと修正プログラムの .exe ファイルの一覧にこのコードのアドレスを追加します。 32 ビットおよび 64 ビット環境では、リンカーは、アドレスを通知するサンクを生成します。 32 ビット環境では、サンクはようになります。  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 ここで`imp_func1`のアドレス、 `func1` .exe ファイルのインポート アドレス テーブル内のスロット。 このため、すべてのアドレスはリンカーに認識します。 ローダーは、正常に動作するすべての読み込み時に、.exe ファイルのインポート アドレス テーブルを更新するだけにできます。  
  
 したがってを使用して **_declspec**が必要ない場合、リンカーがサンクを生成しないためにお勧めします。 サンクを大きくコード (RISC システムでできますいくつかの手順) し、キャッシュのパフォーマンスが低下することができます。 コンパイラに通知する DLL には、関数は場合、間接的な呼び出しを生成できます。  
  
 これでこのコードに示します。  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 この命令が生成されます。  
  
```  
call DWORD PTR __imp_func1  
```  
  
 存在しないサンク`jmp`命令、コード サイズが小さく、高速なためです。  
  
 その一方で、DLL 内部には、関数の呼び出しのたくない間接呼び出しを使用しています。 関数のアドレスを知っています。 時間と領域が必要なための読み込みし、間接的な呼び出しの前に関数のアドレスを格納する、直接の呼び出しは常により高速で小さいです。 使用する場合のみ **_declspec (dllimport)** DLL 自体の外部から DLL 関数を呼び出すとき。 使用しないでください **_declspec (dllimport)** 関数を DLL 内部にその DLL のビルド時にします。  
  
## <a name="see-also"></a>関連項目  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)