---
title: C++ におけるマーシャ リングの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76f6721ce4561e9c2b4323fef9c2eed3231f73cb
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079161"
---
# <a name="overview-of-marshaling-in-c"></a>C++ におけるマーシャリングの概要
混合モードでは、ネイティブ型とマネージ型の間でデータをマーシャリングすることが必要な場合があります。 Visual Studio 2008 が導入された、*マーシャ リング ライブラリ*のためをマーシャ リングし、単純な方法でデータを変換します。  マーシャ リング ライブラリは一連の関数と`marshal_context`一般的な種類のマーシャ リングを実行するクラス。 これらのヘッダー内で、ライブラリが定義されている、**含める/msclr**ディレクトリを Visual Studio のエディション。

|Header|説明|  
|---------------|-----------------|
|marshal.h|`marshal_context` クラスとマーシャ リングの関数のコンテキストに依存しません。|
|marshal_atl.h| ATL 型のマーシャ リング関数|
|marshal_cppstd.h|標準 C++ 型をマーシャ リングするための関数|
|marshal_windows.h|Windows の型をマーシャ リングするための関数|


既定のパス**msclr**フォルダーは、次のようにいずれかのエディションに応じてがあり、ビルド番号。

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

 マーシャ リング ライブラリを使用するには、有無、 [marshal_context クラス](../dotnet/marshal-context-class.md)です。 一部の変換では、コンテキストが必要です。 使用して、その他の変換を実装することができます、 [marshal_as](../dotnet/marshal-as.md)関数。 次の表は、現在サポートされている変換と、コンテキストが必要かどうか、含める必要があるマーシャリング ファイルを示しています。  
  
|変換前の型|変換後の型|マーシャリング メソッド|インクルード ファイル|  
|---------------|-------------|--------------------|------------------|  
|System::String^|const char*|marshal_context|marshal.h|  
|const char*|System::String^|marshal_as|marshal.h|  
|char*|System::String^|marshal_as|marshal.h|  
|System::String^|const wchar_t*|marshal_context|marshal.h|  
|const wchar_t *|System::String^|marshal_as|marshal.h|  
|wchar_t*|System::String^|marshal_as|marshal.h|  
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|  
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|  
|System::String^|BSTR|marshal_context|marshal_windows.h|  
|BSTR|System::String^|marshal_as|marshal.h|  
|System::String^|bstr_t|marshal_as|marshal_windows.h|  
|bstr_t|System::String^|marshal_as|marshal_windows.h|  
|System::String^|std::string|marshal_as|marshal_cppstd.h|  
|std::string|System::String^|marshal_as|marshal_cppstd.h|  
|System::String^|std::wstring|marshal_as|marshal_cppstd.h|  
|std::wstring|System::String^|marshal_as|marshal_cppstd.h|  
|System::String^|CStringT\<char >|marshal_as|marshal_atl.h|  
|CStringT\<char >|System::String^|marshal_as|marshal_atl.h|  
|System::String^|CStringT<wchar_t>|marshal_as|marshal_atl.h|  
|CStringT<wchar_t>|System::String^|marshal_as|marshal_atl.h|  
|System::String^|CComBSTR|marshal_as|marshal_atl.h|  
|CComBSTR|System::String^|marshal_as|marshal_atl.h|  
  
 マーシャリングにコンテキストが必要なのは、マネージ データ型からネイティブ データ型にマーシャリングし、変換先のネイティブ型に自動クリーンアップ用のデストラクターがない場合のみです。 マーシャリング コンテキストは、デストラクターの中で割り当てられているネイティブ データ型を破棄します。 したがって、コンテキストを必要とする変換は、コンテキストが削除されるまでしか有効ではありません。 マーシャリングされた値を保存するには、独自の変数に値をコピーする必要があります。  
  
> [!NOTE]
>  文字列に `NULL` が埋め込まれている場合、文字列のマーシャリング結果は保証されません。 埋め込まれた `NULL` により、文字列が切り詰められたり残されたりする場合があります。  
  
次の例では、インクルード ヘッダー宣言で msclr ディレクトリをインクルードする方法を示しています。  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 マーシャリング ライブラリは、独自のマーシャリング型を追加できるように拡張できます。 マーシャ リング ライブラリを拡張する方法の詳細については、次を参照してください。[する方法: マーシャ リング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)です。  
  
 以前のバージョンでしたマーシャ リングするデータを使用して[プラットフォーム呼び出し](/dotnet/framework/interop/consuming-unmanaged-dll-functions)です。 詳細については`PInvoke`を参照してください[マネージ コードからネイティブ関数を呼び出して](../dotnet/calling-native-functions-from-managed-code.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)   
 [方法: マーシャリング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)
