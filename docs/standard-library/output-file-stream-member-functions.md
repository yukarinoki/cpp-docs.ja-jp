---
title: 出力ファイル ストリームのメンバー関数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab1d229f2c1933025993aa1bc3a3a8b91b41a2cc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195816"
---
# <a name="output-file-stream-member-functions"></a>出力ファイル ストリームのメンバー関数

出力ストリームのメンバー関数は、マニピュレーターと同等のタイプ、書式設定されていない書き込み操作を実行するタイプ、それ以外はストリーム状態を変更し、同等のマニピュレーターまたは挿入演算子を持たないタイプの 3 つがあります。 書式設定された順次出力の場合、挿入演算子とマニピュレーターのみを使用することがあります。 ランダム アクセス バイナリ ディスク出力の場合、挿入演算子の有無を問わず、他のメンバー関数を使用します。

## <a name="the-open-function-for-output-streams"></a>出力ストリームの open 関数

出力ファイル ストリームを使用する ([ofstream](../standard-library/basic-ofstream-class.md))、コンス トラクターで特定のディスク ファイルは、そのストリームを関連付ける必要がありますまたは`open`関数。 使用する場合、`open`関数では、一連のファイルを同じストリーム オブジェクトを再利用することができます。 いずれの場合も、ファイルを記述する引数は同じです。

通常指定する出力ストリームに関連付けられているファイルを開くときに、`open_mode`フラグ。 `ios` クラスで列挙子として定義されているこれらのフラグを、ビットごとの OR ( &#124; ) 演算子と組み合わせることができます。 列挙子のリストについては、「[ios_base::openmode](../standard-library/ios-base-class.md#openmode)」を参照してください。

3 つの一般的な出力ストリームの状況では、モード オプションが関連します。

- ファイルを作成します。 ファイルが既に存在する場合は、古いバージョンが削除されます。

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- 既存のファイルにレコードを追加するか、存在しない場合はファイルを作成します。

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- 同じストリームで一度に 1 つずつ、2 のファイルを開きます。

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>Put

**put** 関数は、1 つの文字を出力ストリームに書き込みます。 次の 2 つのステートメントは既定では同じですが、2 番目は、ストリームの format 引数の影響を受けます。

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>書き込み

`write`関数が、出力ファイル ストリームにメモリのブロックを書き込みます。 length 引数は、書き込まれるバイト数を指定します。 この例は、出力ファイル ストリームを作成し、`Date` 構造体のバイナリ値をそれに書き込みます。

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

`write`関数では、完全なクラス構造を記述するため、null 文字に達したときは停止しません。 この関数は 2 つの引数を受け取ります。 **char**ポインターと、書き込む文字の数。 必須のキャストに注意してください**char** <strong>\*</strong>構造オブジェクトのアドレスの前にします。

## <a name="the-seekp-and-tellp-functions"></a>seekp 関数と tellp 関数

出力ファイル ストリームは、データを次に書き込む位置を指す内部ポインターを保持します。 `seekp` メンバー関数は、このポインターを設定し、それによりランダム アクセス ディスク ファイル出力を提供します。 `tellp` メンバー関数は、ファイル位置を返します。 `seekp` と `tellp` に同等の入力ストリーム関数を使用する例については、「[seekg 関数と tellg 関数](../standard-library/input-stream-member-functions.md)」を参照してください。

## <a name="the-close-function-for-output-streams"></a>出力ストリームの close 関数

`close`メンバー関数は、出力ファイル ストリームに関連付けられているディスク ファイルを閉じます。 すべてのディスク出力を完了するには、ファイルを閉じる必要があります。 必要に応じて、`ofstream`デストラクターでは、ファイルを閉じ、使用することが、`close`を同じストリーム オブジェクトの別のファイルを開く必要がある場合に機能します。

出力ストリーム デストラクターが自動的に閉じるストリームのファイルのみの場合、コンス トラクターまたは`open`メンバー関数は、ファイルを開きます。 既に開いているファイルまたは使用のファイル記述子をコンス トラクターに渡す場合、`attach`メンバー関数は、ファイルを明示的に閉じる必要があります。

## <a name="vclrferrorprocessingfunctionsanchor10"></a> エラー処理関数

ストリームへの書き込み中にエラーがないかテストするには、これらのメンバー関数を使用します。

|関数|戻り値|
|--------------|------------------|
|[bad](basic-ios-class.md#bad)|回復不可能なエラーがある場合は **true**。|
|[fail](basic-ios-class.md#fail)|回復不可能なエラーがある場合、または変換エラーなどの "予想された" 状態である場合、またはファイルが見つからない場合は **true** を返します。 呼び出しの後に処理を再開できる多くの場合、 `clear` 0 個の引数を使用します。|
|[good](basic-ios-class.md#good)|エラー条件 (回復不可能かどうかを問わず) がなく、ファイルの終わりフラグが設定されていない場合は **true** を返します。|
|[eof](basic-ios-class.md#eof)|ファイルの終わり条件で **true** を返します。|
|[clear](basic-ios-class.md#clear)|内部エラー状態を設定します。 既定の引数を指定して呼び出すと、すべてのエラー ビットがクリアされます。|
|[rdstate](basic-ios-class.md #rdstate|現在のエラー状態を返します。|

**!** 同じ機能を実行する演算子をオーバー ロード、`fail`関数。 したがって次のような式があるとします。

```cpp
if(!cout)...
```

上の式は、下の式と同等です。

```cpp
if(cout.fail())...
```

**Void\*()** 演算子がオーバー ロードの逆の処理、 **!** 演算子。したがって、式:

```cpp
if(cout)...
```

上の式は、下の式と同等です。

```cpp
if(!cout.fail())...
```

**Void\*()** 演算子は等しくありません`good`ファイルの終わりをテストしないためです。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)<br/>
