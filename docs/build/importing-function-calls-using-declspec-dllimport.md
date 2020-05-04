---
title: __declspec(dllimport) を使った関数呼び出しのインポート
description: DLL のデータと関数を呼び出すときに __declspec (dllimport) を使用する方法と理由。
ms.date: 05/03/2020
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 515fbdb2824c1eaf41e822adeae1a16d3072eec4
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765722"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>インポート (関数呼び出しを)`__declspec(dllimport)`

を使用して呼び出し**`__declspec(dllimport)`** に注釈を付けると、処理が速くなります。 **`__declspec(dllimport)`** は、エクスポートされた DLL データにアクセスするために常に必要です。

## <a name="import-a-function-from-a-dll"></a>DLL から関数をインポートする

次のコード例は、を使用**`__declspec(dllimport)`** して DLL からアプリケーションに関数呼び出しをインポートする方法を示しています。 は、 `func1` **main**関数を含む実行可能ファイルとは別の DLL 内の関数であると仮定します。

を**`__declspec(dllimport)`** 使用しない場合は、次のコードを指定します。

```C
int main(void)
{
   func1();
}
```

コンパイラは、次のようなコードを生成します。

```asm
call func1
```

この呼び出しは、リンカーによって次のように変換されます。

```asm
call 0x4000000         ; The address of 'func1'.
```

が`func1`別の DLL 内に存在する場合、リンカーはの`func1`アドレスを知る方法がないため、このアドレスを直接解決することはできません。 32ビット環境と64ビット環境では、リンカーは既知のアドレスでサンクを生成します。 32ビット環境では、サンクは次のようになります。

```asm
0x40000000:    jmp DWORD PTR __imp_func1
```

実行`__imp_func1`可能ファイルのインポートアドレス`func1`テーブルのスロットのアドレスを次に示します。 これらのアドレスはすべてリンカーに知られています。 ローダーは、すべてが正常に機能するためには、読み込み時に実行可能ファイルのインポートアドレステーブルを更新するだけで済みます。

このため、を**`__declspec(dllimport)`** 使用することをお勧めします。これは、リンカーが不要な場合にサンクを生成しないためです。 サンクによってコードが大きくなり (RISC システムでは複数の命令になる可能性があります)、キャッシュのパフォーマンスが低下する可能性があります。 コンパイラに対して、関数が DLL 内にあることを通知すると、間接的な呼び出しが生成される可能性があります。

ここで、次のコードを示します。

```C
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

では、次の命令が生成されます。

```asm
call DWORD PTR __imp_func1
```

サンクと`jmp`命令がないため、コードのサイズが小さくなり、高速になります。 プログラム全体の最適化を使用しなく**`__declspec(dllimport)`** ても、同じ効果を得ることができます。 詳細については、「[/GL (プログラム全体の最適化)](reference/gl-whole-program-optimization.md)」を参照してください。

DLL 内の関数呼び出しでは、間接的な呼び出しを使用する必要はありません。 リンカーは既に関数のアドレスを認識しています。 間接的な呼び出しの前に、関数のアドレスを読み込んで保存するための追加の時間と領域が必要になります。 直接呼び出しは、常に高速でより小さくなります。 Dll 自体の外部から**`__declspec(dllimport)`** dll 関数を呼び出すときにのみ、を使用します。 Dll の**`__declspec(dllimport)`** ビルド時に dll 内の関数を使用しないでください。

## <a name="see-also"></a>関連項目

[アプリケーションへのインポート](importing-into-an-application.md)
