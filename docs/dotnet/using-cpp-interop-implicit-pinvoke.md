---
title: C++ Interop (暗黙の PInvoke) の使用
ms.date: 11/04/2016
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
ms.openlocfilehash: d26fbefd87b3ba6d6ca7e183be78608777f383b5
ms.sourcegitcommit: 27d9db019f6d84c94de9e6aff0170d918cee6738
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "79545421"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Interop (暗黙の PInvoke) の使用

他の .NET 言語とはC++異なり、ビジュアルには相互運用性のサポートがあります。これにより、マネージコードとアンマネージコードは同じアプリケーションに存在し、同じファイル内に存在していてもかまいません ([マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)プラグマを含む)。 これにより、Visual C++ 開発者は、他のアプリケーションの動作を妨げることなく、既存の Visual C++ アプリケーションに .NET 機能を統合できます。

また、 [dllexport、dllimport](../cpp/dllexport-dllimport.md)を使用して、マネージコンパイル単位からアンマネージ関数を呼び出すこともできます。

関数パラメーターのマーシャリング方法を指定したり、DllImportAttribute を明示的に呼び出す際に指定できるその他の詳細設定を行ったりする必要がない場合は、暗黙の PInvoke を使用すると便利です。

Visual C++ では、マネージド関数とアンマネージド 関数を相互運用するために 2 つの方法があります。

- [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

明示的な PInvoke は、.NET Framework でサポートされており、ほとんどの .NET 言語で使用できます。 ただし、その名前からわかるように、C++ Interop は Visual C++ 固有の機能です。

## <a name="c-interop"></a>C++ Interop

C++相互運用機能により、タイプセーフが向上し、通常は実装が煩雑になります。 ただし、 C++アンマネージソースコードを使用できない場合、またはクロスプラットフォームプロジェクトの場合は、相互運用はオプションではありません。

## <a name="c-com-interop"></a>C++ COM Interop

Visual C++ がサポートしている相互運用機能は、COM コンポーネントとの相互運用性において、他の .NET 言語に比べ特に優れた効果を発揮します。 データ型の制限付きサポート、すべての COM インターフェイスのすべてのメンバーの必須の公開など、 [tlbimp.exe (タイプライブラリインポーター)](/dotnet/framework/tools/tlbimp-exe-type-library-importer).NET Framework の制限に限定されるのではなくC++ 、相互運用機能では、com コンポーネントへのアクセスが可能であり、個別の相互運用機能アセンブリは必要ありません。 Visual Basic とC#は異なり、 C++ビジュアルは通常の com 機構 ( **CoCreateInstance**や**QUERYINTERFACE**など) を使用して com オブジェクトを直接使用できます。 これが可能なのC++は、相互運用機能によって、マネージ関数からアンマネージ関数に移行するための遷移コードが、コンパイラによって自動的に挿入されるためです。

相互C++運用機能を使用すると、COM コンポーネントは通常使用されるか、またはC++クラス内にラップすることができます。 これらのラッパークラスはカスタムランタイム呼び出し可能ラッパー (CRCWs) と呼ばれ、アプリケーションコードで直接 COM を使用する場合よりも2つの利点があります。

- 生成されたクラスは、ビジュアルC++以外の言語から使用できます。

- COM インターフェイスの詳細は、マネージクライアントコードからは非表示にすることができます。 .NET データ型はネイティブ型の代わりに使用できます。データマーシャリングの詳細は、CRCW 内で透過的に実行できます。

COM が直接使用されるか、CRCW を介して使用されるかに関係なく、単純な blittable 型以外の引数の型をマーシャリングする必要があります。

## <a name="blittable-types"></a>blittable 型

単純な組み込み型を使用するアンマネージ Api の場合 (「 [Blittable 型と非 Blittable 型](/dotnet/framework/interop/blittable-and-non-blittable-types)」を参照)、これらのデータ型はメモリ内で同じ表現を使用しますが、より複雑なデータ型には明示的なデータマーシャリングが必要であるため、特別なコーディングは必要ありません。 例については、「[方法: PInvoke を使用してマネージコードからネイティブ dll を呼び出す](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)」を参照してください。

## <a name="example"></a>例

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>このセクションの内容

- [方法: C++ Interop を使用して ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して構造体をマーシャリングする](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [方法: C++ Interop を使用して配列をマーシャリングする](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [方法: C++ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [方法: System::String の文字にアクセスする](../dotnet/how-to-access-characters-in-a-system-string.md)

- [方法: char * 文字列を System::Byte 配列に変換する](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [方法: System:: String を wchar_t * または char\* に変換する](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [方法: System::String を標準文字列に変換する](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [方法: 標準文字列を System::String に変換する](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [方法 : バイト配列へのポインターを取得する](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [方法: アンマネージ リソースをバイト配列に読み込む](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [方法: ネイティブ関数の参照クラスを変更する](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [方法: イメージがネイティブであるか CLR であるかを確認する](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [方法: 値型への参照をネイティブ型で保持する](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [方法: アンマネージ メモリ内にオブジェクト参照を保持する](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [方法:/clr コンパイルを検出する](../dotnet/how-to-detect-clr-compilation.md)

- [方法: System::Guid と _GUID の間で変換を行う](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [方法: out パラメーターを指定する](../dotnet/how-to-specify-an-out-parameter.md)

- [方法:/clr コンパイルでネイティブ型を使用する](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)

- [方法: ネイティブ クラスを C# で使用できるようにラップする](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

相互運用シナリオでデリゲートを使用する方法の詳細については、「 [delegate (C++コンポーネント拡張)](../extensions/delegate-cpp-component-extensions.md)」を参照してください。

## <a name="see-also"></a>参照

- [マネージド コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)
