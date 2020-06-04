---
title: '方法: PInvoke を使用してマネージド コードからネイティブ DLL を呼び出す'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: 1eb5d5669c49dd49a411c275f8845dbbab989df3
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545091"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>方法: PInvoke を使用してマネージド コードからネイティブ DLL を呼び出す

アンマネージ Dll で実装されている関数は、プラットフォーム呼び出し (P/Invoke) 機能を使用してマネージコードから呼び出すことができます。 DLL のソースコードが使用できない場合は、相互運用のための唯一のオプションとして P/Invoke が使用されます。 ただし、他の .NET 言語とはC++異なり、Visual は P/Invoke の代わりに使用できます。 詳細については、「 [Interop (暗黙のC++ PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。

## <a name="example"></a>例

次のコード例では、Win32 [GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)関数を使用して、画面の現在の解像度をピクセル単位で取得します。

引数と戻り値として組み込み型のみを使用する関数の場合、追加の処理は必要ありません。 関数ポインター、配列、構造体などの他のデータ型では、適切なデータマーシャリングを保証するために、追加の属性が必要です。

必須ではありませんが、この例で示すように、P/Invoke 宣言を値クラスの静的メンバーにして、グローバル名前空間に存在しないようにすることをお勧めします。

```cpp
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>参照

[C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
