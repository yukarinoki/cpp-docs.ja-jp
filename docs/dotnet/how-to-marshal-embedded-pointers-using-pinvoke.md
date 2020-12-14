---
description: '詳細については、「方法: PInvoke を使用して埋め込みポインターをマーシャリングする」を参照してください。'
title: '方法: PInvoke を使用して埋め込みポインターをマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: d31660a9a8ba345b380d442bb4484e332fe9d7cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302557"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>方法: PInvoke を使用して埋め込みポインターをマーシャリングする

アンマネージ Dll で実装されている関数は、プラットフォーム呼び出し (P/Invoke) 機能を使用してマネージコードから呼び出すことができます。 DLL のソースコードが使用できない場合は、相互運用のための唯一のオプションとして P/Invoke が使用されます。 ただし、他の .NET 言語とは異なり、Visual C++ は P/Invoke の代わりに使用できます。 詳細については、「 [C++ interop (暗黙的な PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md) 」および「 [方法: C++ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)」を参照してください。

## <a name="example"></a>例

ネイティブコードに構造体を渡すには、ネイティブ構造体へのデータレイアウトと同等のマネージ構造体が作成されている必要があります。 ただし、ポインターを含む構造体では、特別な処理が必要です。 ネイティブ構造体の各埋め込みポインターについて、構造体のマネージバージョンに型のインスタンスが含まれている必要があり <xref:System.IntPtr> ます。 また、これらのインスタンスのメモリは、、、およびの各メソッドを使用して明示的に割り当て、初期化、および解放する必要があり <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A> <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> ます。

次のコードは、アンマネージモジュールとマネージモジュールで構成されています。 アンマネージモジュールは、ポインターを含む ListString という構造体と、TakesListStruct と呼ばれる関数を定義する DLL です。 マネージモジュールは、TakesListStruct 関数をインポートするコマンドラインアプリケーションであり、double * がインスタンスで表される点を除いて、ネイティブ ListStruct と同等の MListStruct という構造体を定義し <xref:System.IntPtr> ます。 Main 関数は、TakesListStruct を呼び出す前に、このフィールドが参照するメモリを割り当て、初期化します。

```cpp
// TraditionalDll6.cpp
// compile with: /EHsc /LD
#include <stdio.h>
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct ListStruct {
   int count;
   double* item;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API void TakesListStruct(ListStruct);
}

void TakesListStruct(ListStruct list) {
   printf_s("[unmanaged] count = %d\n", list.count);
   for (int i=0; i<list.count; i++)
      printf_s("array[%d] = %f\n", i, list.item[i]);
}
```

```cpp
// EmbeddedPointerMarshalling.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MListStruct {
   int count;
   IntPtr item;
};

value struct TraditionalDLL {
    [DllImport("TraditionalDLL6.dll")]
   static public void TakesListStruct(MListStruct);
};

int main() {
   array<double>^ parray = gcnew array<double>(10);
   Console::WriteLine("[managed] count = {0}", parray->Length);

   Random^ r = gcnew Random();
   for (int i=0; i<parray->Length; i++) {
      parray[i] = r->NextDouble() * 100.0;
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);
   }

   int size = Marshal::SizeOf(double::typeid);
   MListStruct list;
   list.count = parray->Length;
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);

   for (int i=0; i<parray->Length; i++) {
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);
      Marshal::StructureToPtr(parray[i], t, false);
   }

   TraditionalDLL::TakesListStruct( list );
   Marshal::FreeCoTaskMem(list.item);
}
```

DLL の一部は、従来の #include ディレクティブを使用してマネージコードに公開されないことに注意してください。 実際、DLL は実行時にのみアクセスされるため、でインポートされた関数に関する問題 <xref:System.Runtime.InteropServices.DllImportAttribute> はコンパイル時に検出されません。

## <a name="see-also"></a>関連項目

[C++ での明示的な PInvoke の使用 (DllImport 属性)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
