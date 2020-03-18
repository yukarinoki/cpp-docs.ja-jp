---
title: __declspec(dllimport) を使用した関数呼び出しのインポート
ms.date: 11/04/2016
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 1743cbba8c3046ef844f16be8e78d43c61f62606
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442510"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>__declspec(dllimport) を使用した関数呼び出しのインポート

次のコード例は、 **_declspec (dllimport)** を使用して、DLL からアプリケーションに関数呼び出しをインポートする方法を示しています。 `func1` が、 **main**関数を含む .exe ファイルとは別の DLL に存在する関数であると仮定します。

**__Declspec (dllimport)** を使用しない場合は、次のコードを指定します。

```
int main(void)
{
   func1();
}
```

コンパイラは、次のようなコードを生成します。

```
call func1
```

この呼び出しは、リンカーによって次のように変換されます。

```
call 0x4000000         ; The address of 'func1'.
```

`func1` 別の DLL に存在する場合は、`func1` のアドレスを知る方法がないため、リンカーはこれを直接解決できません。 16ビット環境では、リンカーはこのコードアドレスを .exe ファイル内のリストに追加します。これは、ローダーが実行時に正しいアドレスを使用して修正されることを示します。 32ビット環境と64ビット環境では、リンカーによって、アドレスを認識するサンクが生成されます。 32ビット環境では、サンクは次のようになります。

```
0x40000000:    jmp DWORD PTR __imp_func1
```

ここで `imp_func1` は、.exe ファイルのインポートアドレステーブルの `func1` スロットのアドレスです。 このため、すべてのアドレスがリンカーに知られています。 ローダーは、すべてが正常に機能するためには、読み込み時に .exe ファイルのインポートアドレステーブルを更新するだけで済みます。

したがって、 **__declspec (dllimport)** を使用することをお勧めします。これは、必要でない場合に、リンカーがサンクを生成しないためです。 サンクによってコードが大きくなり (RISC システムでは複数の命令になる可能性があります)、キャッシュのパフォーマンスが低下する可能性があります。 コンパイラに対して、関数が DLL 内にあることを通知すると、間接的な呼び出しが生成される可能性があります。

ここで、次のコードを示します。

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

では、次の命令が生成されます。

```
call DWORD PTR __imp_func1
```

サンクと `jmp` 命令は存在しないため、コードのサイズは小さくなり、高速になります。

一方、DLL 内の関数呼び出しでは、間接呼び出しを使用する必要はありません。 関数のアドレスは既にわかっています。 間接的な呼び出しの前に、関数のアドレスを読み込んで格納するために時間と領域が必要になるため、直接呼び出しは常に高速でより小さくなります。 Dll 自体の外部から DLL 関数を呼び出すときは、 **__declspec (dllimport)** のみを使用する必要があります。 Dll のビルド時に DLL 内の関数に **__declspec (dllimport)** を使用しないでください。

## <a name="see-also"></a>参照

[アプリケーションへのインポート](importing-into-an-application.md)
