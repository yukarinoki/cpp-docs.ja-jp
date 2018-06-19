---
title: C++ (DllImport 属性) で明示的な PInvoke を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82215e4815d25dd116cf930be9cc0f40da761bf8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169505"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>C++ での明示的な PInvoke (DllImport 属性) の使用方法 
.NET Framework では、明示的なプラットフォーム呼び出し (PInvoke) 機能に、マネージ アプリケーションが DLL 内部にパッケージ化されているアンマネージ関数を呼び出すことができるようにする `Dllimport` 属性を備えています。 明示的な PInvoke は、アンマネージ API が DLL としてパッケージ化され、ソース コードが利用できない場合に必要です。 たとえば、Win32 関数の呼び出しには、PInvoke が必要です。 それ以外の場合、暗黙的な P を使用して {Invoke; 参照してください[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)詳細についてはします。  
  
 PInvoke を機能させるには、<xref:System.Runtime.InteropServices.DllImportAttribute> を使用します。 この属性は、その最初の引数として DLL 名を使用し、使用する各 DLL エントリ ポイントの関数宣言の前に置かれます。 関数のシグネチャは、DLL によってエクスポートされた関数名に一致する必要があります (ただし、型変換によっては、マネージ型を使用して `DllImport` 宣言を定義することで、暗黙的に実行できるものもあります)。  
  
 その結果、これは、必要な遷移コード (または、サンク) と単純データ変換を含む各ネイティブ DLL 関数のマネージ エントリ ポイントになります。 その後、マネージ関数は、これらのエントリ ポイントを介して DLL を呼び出します。 PInvoke の結果として、モジュールに挿入されたコードは完全に管理します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [方法: PInvoke を使用してマネージ コードからネイティブ DLL を呼び出す](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して文字列をマーシャリングする](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して構造体をマーシャリングする](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して配列をマーシャリングする](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して関数ポインターをマーシャリングする](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [方法: PInvoke を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>関連項目  
 [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)