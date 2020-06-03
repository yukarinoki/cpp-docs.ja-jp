---
title: ダブル サンキング (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
ms.openlocfilehash: 89cca9ef42910d295cbae8bb677fb51927dbcdd2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545349"
---
# <a name="double-thunking-c"></a>ダブル サンキング (C++)

ダブルサンキングとは、マネージコンテキストの関数呼び出しがビジュアルC++マネージ関数を呼び出すときに発生するパフォーマンスの低下を指します。プログラムの実行では、マネージ関数を呼び出すために、関数のネイティブエントリポイントを呼び出します。 このトピックでは、2つのサンキングが発生する場所と、パフォーマンスを向上させるためにそれを回避する方法について説明します。

## <a name="remarks"></a>コメント

既定では、 **/clr**を指定してコンパイルすると、マネージ関数の定義によって、コンパイラはマネージエントリポイントとネイティブエントリポイントを生成します。 これにより、マネージ呼び出しサイトからマネージ関数を呼び出すことができます。 ただし、ネイティブエントリポイントが存在する場合は、関数のすべての呼び出しのエントリポイントになることがあります。 呼び出し元の関数がマネージドの場合、ネイティブエントリポイントはマネージエントリポイントを呼び出します。 実際には、関数を呼び出すために2つの呼び出しが必要になります (したがって、ダブルサンキング)。 たとえば、仮想関数は、常にネイティブのエントリポイントを通じて呼び出されます。

解決策の1つとして、マネージ関数のネイティブエントリポイントを生成しないようにコンパイラに指示します。この関数は、 [__clrcall](../cpp/clrcall.md)の呼び出し規約を使用してマネージコンテキストからのみ呼び出されます。

同様に、マネージ関数をエクスポート ([dllexport、dllimport](../cpp/dllexport-dllimport.md)) した場合、ネイティブエントリポイントが生成され、その関数をインポートして呼び出すすべての関数は、ネイティブエントリポイントを通じてを呼び出します。 このような状況でダブルサンキングを回避するには、ネイティブのエクスポート/インポートセマンティクスを使用しないでください。単に `#using` を使用してメタデータを参照します ( [#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)を参照してください)。

不要なダブルサンキングを減らすために、コンパイラが更新されました。 たとえば、シグネチャのマネージ型を持つ関数 (戻り値の型を含む) は、暗黙的に `__clrcall`としてマークされます。

## <a name="example"></a>例

### <a name="description"></a>説明

次の例は、2つのサンキングを示しています。 ネイティブコンパイル ( **/clr**を使用しない) の場合、`main` の仮想関数を呼び出すと、`T`のコピーコンストラクターと1回のデストラクターへの呼び出しが1回生成されます。 同様の動作は、仮想関数が **/clr**および `__clrcall`で宣言されている場合にも実行されます。 ただし、 **/clr**を使用してコンパイルしただけでは、関数呼び出しによってコピーコンストラクターへの呼び出しが生成されますが、ネイティブからマネージドサンクによってコピーコンストラクターへの別の呼び出しが発生します。

### <a name="code"></a>コード

```cpp
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

### <a name="sample-output"></a>サンプル出力

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

前のサンプルでは、ダブルサンキングの存在を示していました。 このサンプルでは、その効果を示します。 `for` ループは仮想関数を呼び出し、プログラムは実行時間を報告します。 プログラムが **/clr**でコンパイルされると、最も時間がかかる時間が報告されます。 **/Clr**を指定せずにコンパイルする場合、または `__clrcall`で仮想関数が宣言されている場合は、最速の時刻が報告されます。

### <a name="code"></a>コード

```cpp
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

### <a name="sample-output"></a>サンプル出力

```
4.2 seconds
after calling struct S
```

## <a name="see-also"></a>参照

[混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
