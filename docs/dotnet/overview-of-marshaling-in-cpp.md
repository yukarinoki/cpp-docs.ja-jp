---
title: C++ におけるマーシャリングの概要
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 0c7bf18fa823c6301a79c3f989efa73c9e8f628a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372007"
---
# <a name="overview-of-marshaling-in-ccli"></a>C++/CLI でのマーシャリングの概要

混合モードでは、ネイティブ型とマネージド型の間でデータをマーシャリングすることが必要な場合があります。 *マーシャリング ライブラリ*を使用すると、簡単な方法でデータをマーシャリングおよび変換できます。  マーシャリング ライブラリは、一連の関数と、共通`marshal_context`型のマーシャリングを実行するクラスで構成されます。 ライブラリは、Visual Studio エディションの**インクルード/msclr**ディレクトリ内の次のヘッダーで定義されます。

|ヘッダー|説明|
|---------------|-----------------|
|marshal.h|`marshal_context`クラスおよびコンテキストフリーのマーシャリング関数|
|marshal_atl.h| ATL 型をマーシャリングするための関数|
|marshal_cppstd.h|標準 C++ 型をマーシャリングするための関数|
|marshal_windows.h|Windows 型をマーシャリングするための関数|

**msclr**フォルダのデフォルトパスは、使用しているエディションとビルド番号に応じて次のようになります。

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

marshal_context [Class](../dotnet/marshal-context-class.md)の有無にかかわらず、マーシャリング ライブラリを使用できます。 一部の変換では、コンテキストが必要です。 その他の変換は[、marshal_as](../dotnet/marshal-as.md)関数を使用して実装できます。 次の表は、現在サポートされている変換と、コンテキストが必要かどうか、含める必要があるマーシャリング ファイルを示しています。

|変換前の型|変換後の型|マーシャリング メソッド|インクルード ファイル|
|---------------|-------------|--------------------|------------------|
|System::String^|定数文字\*|marshal_context|marshal.h|
|定数文字\*|System::String^|marshal_as|marshal.h|
|Char\*|System::String^|marshal_as|marshal.h|
|System::String^|定数wchar_t\*|marshal_context|marshal.h|
|const wchar_t \*|System::String^|marshal_as|marshal.h|
|Wchar_t\*|System::String^|marshal_as|marshal.h|
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
|System::String^|\<>|marshal_as|marshal_atl.h|
|\<>|System::String^|marshal_as|marshal_atl.h|
|System::String^|><wchar_t|marshal_as|marshal_atl.h|
|><wchar_t|System::String^|marshal_as|marshal_atl.h|
|System::String^|CComBSTR|marshal_as|marshal_atl.h|
|CComBSTR|System::String^|marshal_as|marshal_atl.h|

マーシャリングにコンテキストが必要なのは、マネージド データ型からネイティブ データ型にマーシャリングし、変換先のネイティブ型に自動クリーンアップ用のデストラクターがない場合のみです。 マーシャリング コンテキストは、デストラクターの中で割り当てられているネイティブ データ型を破棄します。 したがって、コンテキストを必要とする変換は、コンテキストが削除されるまでしか有効ではありません。 マーシャリングされた値を保存するには、独自の変数に値をコピーする必要があります。

> [!NOTE]
> 文字列に `NULL` が埋め込まれている場合、文字列のマーシャリング結果は保証されません。 埋め込まれた `NULL` により、文字列が切り詰められたり残されたりする場合があります。

次の例では、インクルード ヘッダー宣言で msclr ディレクトリをインクルードする方法を示しています。

`#include "msclr\marshal_cppstd.h"`

マーシャリング ライブラリは、独自のマーシャリング型を追加できるように拡張できます。 マーシャリング ライブラリの拡張の詳細については、「[方法 : マーシャリング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)<br/>
[方法: マーシャリング ライブラリを拡張する](../dotnet/how-to-extend-the-marshaling-library.md)
