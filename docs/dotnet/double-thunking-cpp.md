---
title: ダブル サンク (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 47d5bbbecc8e1b9743c543a503df1a0afa0dc0ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111209"
---
# <a name="double-thunking-c"></a>ダブル サンキング (C++)
ダブル サンキング Visual C マネージ関数とプログラムの実行をここでは、マネージ コンテキスト呼び出し内の関数呼び出しはマネージ関数を呼び出すために、関数のネイティブ エントリ ポイントを呼び出すときに発生する可能性がパフォーマンスの低下を指します。 このトピックでは、ダブル サンキングが発生して、パフォーマンスを向上させることを回避する方法について説明します。  
  
## <a name="remarks"></a>コメント  
 既定でコンパイルするときに **/clr**、マネージ関数の定義には、マネージ エントリ ポイントと、ネイティブ エントリ ポイントを生成するコンパイラです。 これにより、マネージ関数をネイティブおよびマネージ呼び出し側から呼び出すことができます。 ただし、ネイティブ エントリ ポイントが存在する場合、だということ、関数へのすべての呼び出しのエントリ ポイントです。 呼び出し元の関数が管理されている場合、ネイティブ エントリ ポイントは、マネージ エントリ ポイントを呼び出します。 実際には、2 つの呼び出しが関数の呼び出しに必要な (したがって、ダブル サンキング)。 たとえば、仮想関数はネイティブ エントリ ポイントを常に呼び出されます。  
  
 1 つの解決、関数のみから呼び出される管理対象のコンテキストを使用してマネージ関数の場合は、ネイティブ エントリ ポイントを生成しないようにコンパイラに指示するには、 [_ _clrcall](../cpp/clrcall.md)呼び出し規約です。  
  
 同様に、エクスポートする場合 ([dllexport、dllimport](../cpp/dllexport-dllimport.md)) マネージ関数の場合は、ネイティブ エントリ ポイントが生成され、インポートし、その関数を呼び出す関数はネイティブ エントリ ポイントを呼び出します。 このような状況でダブル サンキングを避けるためには、使用しないネイティブ エクスポート/インポート セマンティクスです。使用してメタデータを参照するだけ`#using`(を参照してください[#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md))。  
  
 ダブル サンキングの不要なため、コンパイラが更新されました。 たとえば、マネージ型 (戻り値の型を含む) のシグネチャに含む任意の関数は暗黙的としてマークされます`__clrcall`です。 ダブル サンクの削除の詳細については、次を参照してください。 [ http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx)です。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例では、ダブル サンキングを示します。 ネイティブ コンパイルされたときに (せず **/clr**) での仮想関数への呼び出し`main`1 回の呼び出しを生成`T`のコンス トラクターとデストラクターは、1 回の呼び出しをコピーします。 仮想関数を宣言するときに同様の動作が実現 **/clr**と`__clrcall`です。 ただし、指定してコンパイル **/clr**、関数呼び出しには、コピー コンス トラクターの呼び出しが生成されますが、ネイティブからマネージ サンクのため、コピー コンス トラクターを呼び出します。  
  
### <a name="code"></a>コード  
  
```  
// double_thunking.cpp  
// compile with: /clr  
#include <stdio.h>  
struct T {  
   T() {  
      puts(__FUNCSIG__);  
   }  
  
   T(const T&) {  
      puts(__FUNCSIG__);  
   }  
  
   ~T() {  
      puts(__FUNCSIG__);  
   }  
  
   T& operator=(const T&) {  
      puts(__FUNCSIG__);  
      return *this;  
   }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
  
   printf("calling struct S\n");  
   pS->f(t);  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>出力例  
  
```  
__thiscall T::T(void)  
calling struct S  
__thiscall T::T(const struct T &)  
__thiscall T::T(const struct T &)  
__thiscall T::~T(void)  
__thiscall T::~T(void)  
after calling struct S  
__thiscall T::~T(void)  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 前のサンプルには、ダブル サンキングの存在が示されています。 このサンプルでは、その効果を示します。 `for`ループは、仮想関数とプログラムのレポートの実行時間を呼び出します。 プログラムをコンパイルしたときに、最も低速な時間が報告された **/clr**です。 せずにコンパイルするときに最短の時間が報告される **/clr**と仮想関数が宣言されている場合、または`__clrcall`です。  
  
### <a name="code"></a>コード  
  
```  
// double_thunking_2.cpp  
// compile with: /clr  
#include <time.h>  
#include <stdio.h>   
  
#pragma unmanaged  
struct T {  
   T() {}  
   T(const T&) {}  
   ~T() {}  
   T& operator=(const T&) { return *this; }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
   clock_t start, finish;  
   double  duration;  
   start = clock();  
  
   for ( int i = 0 ; i < 1000000 ; i++ )  
      pS->f(t);  
  
   finish = clock();  
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);  
   printf( "%2.1f seconds\n", duration );  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>出力例  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)