---
description: 詳細については、「C++ での明示的な PInvoke の使用 (DllImport 属性)」を参照してください。
title: 'C++ での明示的な PInvoke (DllImport 属性) の使用方法 '
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: 6c49195cdb677474809435a5bd826808260680e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305476"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++ での明示的な PInvoke (DllImport 属性) の使用方法 

.NET Framework では、明示的なプラットフォーム呼び出し (PInvoke) 機能に、マネージド アプリケーションが DLL 内部にパッケージ化されているアンマネージド 関数を呼び出すことができるようにする `Dllimport` 属性を備えています。 明示的な PInvoke は、アンマネージ API が DLL としてパッケージ化され、ソース コードが利用できない場合に必要です。 たとえば、Win32 関数の呼び出しには、PInvoke が必要です。 それ以外の場合は、暗黙の P {Invoke; を使用します。詳細については、「 [C++ Interop の使用 (暗黙的な PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) 」を参照してください。

PInvoke を機能させるには、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用します。 この属性は、その最初の引数として DLL 名を使用し、使用する各 DLL エントリ ポイントの関数宣言の前に置かれます。 関数のシグネチャは、DLL によってエクスポートされた関数名に一致する必要があります (ただし、型変換によっては、マネージド型を使用して `DllImport` 宣言を定義することで、暗黙的に実行できるものもあります)。

その結果、これは、必要な遷移コード (または、サンク) と単純データ変換を含む各ネイティブ DLL 関数のマネージド エントリ ポイントになります。 その後、マネージド関数は、これらのエントリ ポイントを介して DLL を呼び出します。 PInvoke の結果としてモジュールに挿入されたコードは、完全に管理されます。

## <a name="in-this-section"></a>このセクションの内容

- [呼び出し (マネージコードからネイティブ関数を)](../dotnet/calling-native-functions-from-managed-code.md)

- [方法: PInvoke を使用してマネージコードからネイティブ Dll を呼び出す](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [方法: PInvoke を使用して文字列をマーシャリングする](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [方法: PInvoke を使用して構造体をマーシャリングする](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [方法: PInvoke を使用して配列をマーシャリングする](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [方法: PInvoke を使用して関数ポインターをマーシャリングする](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [方法: PInvoke を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>関連項目

[呼び出し (マネージコードからネイティブ関数を)](../dotnet/calling-native-functions-from-managed-code.md)
