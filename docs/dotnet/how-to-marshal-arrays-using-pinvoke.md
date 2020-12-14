---
description: '詳細については、「方法: PInvoke を使用して配列をマーシャリングする」を参照してください。'
title: '方法: PInvoke を使用して配列をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 90fd7b2cbefe2fb3621f512d49fbc088240922a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258226"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>方法: PInvoke を使用して配列をマーシャリングする

このトピックでは、 <xref:System.String> .NET Framework プラットフォーム呼び出しサポートを使用して CLR 文字列型を使用して、C スタイルの文字列を受け入れるネイティブ関数を呼び出す方法について説明します。 Visual C++ プログラマは、(可能な場合は) 代わりに C++ 相互運用機能を使用することをお勧めします。これは、P/Invoke ではコンパイル時のエラー報告がほとんどなく、タイプセーフではなく、実装が面倒な場合があるためです。 アンマネージ API が DLL としてパッケージ化されていて、ソースコードが使用できない場合は、P/Invoke が唯一のオプションです (それ以外の場合は、「 [C++ Interop (暗黙的な PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください)。

## <a name="example"></a>例

ネイティブ配列とマネージ配列は、メモリ内に異なる方法で配置されるため、マネージ/アンマネージ境界を越えて正常に渡されるには、変換またはマーシャリングが必要です。 このトピックでは、単純な (blitable) 項目の配列をマネージコードからネイティブ関数に渡す方法について説明します。

一般に、マネージ/アンマネージデータマーシャリングの場合と同様に、属性を使用して、 <xref:System.Runtime.InteropServices.DllImportAttribute> 使用する各ネイティブ関数のマネージエントリポイントを作成します。 引数として配列を受け取る関数の場合は、 <xref:System.Runtime.InteropServices.MarshalAsAttribute> データのマーシャリング方法をコンパイラに指定するために、属性も使用する必要があります。 次の例では、 <xref:System.Runtime.InteropServices.UnmanagedType> マネージ配列が C スタイルの配列としてマーシャリングされることを示すために、列挙体が使用されています。

次のコードは、アンマネージモジュールとマネージモジュールで構成されています。 アンマネージモジュールは、整数の配列を受け取る関数を定義する DLL です。 2番目のモジュールは、この関数をインポートするマネージコマンドラインアプリケーションですが、マネージ配列で定義します。また、属性を使用して、 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 呼び出されたときに配列がネイティブ配列に変換されることを指定します。

マネージモジュールは、/clr を使用してコンパイルされます。

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

DLL の一部は、従来の #include ディレクティブを通じてマネージコードに公開されないことに注意してください。 実際、DLL は実行時にのみアクセスされるため、でインポートされた関数に関する問題 <xref:System.Runtime.InteropServices.DllImportAttribute> はコンパイル時に検出されません。

## <a name="see-also"></a>関連項目

[C++ での明示的な PInvoke の使用 (DllImport 属性)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
