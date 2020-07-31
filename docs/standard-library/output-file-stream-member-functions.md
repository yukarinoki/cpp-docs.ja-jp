---
title: 出力ファイル ストリームのメンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: f20ed4e238d23211a6eeec4a3091daeb4d02a9b3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217676"
---
# <a name="output-file-stream-member-functions"></a>出力ファイル ストリームのメンバー関数

出力ストリームのメンバー関数は、マニピュレーターと同等のタイプ、書式設定されていない書き込み操作を実行するタイプ、それ以外はストリーム状態を変更し、同等のマニピュレーターまたは挿入演算子を持たないタイプの 3 つがあります。 書式設定された順次出力の場合、挿入演算子とマニピュレーターのみを使用することがあります。 ランダム アクセス バイナリ ディスク出力の場合、挿入演算子の有無を問わず、他のメンバー関数を使用します。

## <a name="the-open-function-for-output-streams"></a>出力ストリームの open 関数

出力ファイルストリーム ([ofstream](../standard-library/basic-ofstream-class.md)) を使用するには、そのストリームをコンストラクターまたは関数内の特定のディスクファイルに関連付ける必要があり `open` ます。 関数を使用する場合は、 `open` 一連のファイルで同じストリームオブジェクトを再利用できます。 いずれの場合も、ファイルを記述する引数は同じです。

出力ストリームに関連付けられているファイルを開く場合は、通常、フラグを指定し `open_mode` ます。 `ios` クラスで列挙子として定義されているこれらのフラグを、ビットごとの OR ( &#124; ) 演算子と組み合わせることができます。 列挙子のリストについては、「[ios_base::openmode](../standard-library/ios-base-class.md#openmode)」を参照してください。

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

関数は、 `write` メモリブロックを出力ファイルストリームに書き込みます。 length 引数は、書き込まれるバイト数を指定します。 この例は、出力ファイル ストリームを作成し、`Date` 構造体のバイナリ値をそれに書き込みます。

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

`write`関数は null 文字に到達すると停止しないため、完全なクラス構造が書き込まれます。 関数は、ポインターと書き込む文字数の2つの引数を受け取り **`char`** ます。 **`char`** <strong>\*</strong> 構造体オブジェクトのアドレスの前に必要なキャストに注意してください。

## <a name="the-seekp-and-tellp-functions"></a>seekp 関数と tellp 関数

出力ファイル ストリームは、データを次に書き込む位置を指す内部ポインターを保持します。 `seekp` メンバー関数は、このポインターを設定し、それによりランダム アクセス ディスク ファイル出力を提供します。 `tellp` メンバー関数は、ファイル位置を返します。 `seekp` と `tellp` に同等の入力ストリーム関数を使用する例については、「[seekg 関数と tellg 関数](../standard-library/input-stream-member-functions.md)」を参照してください。

## <a name="the-close-function-for-output-streams"></a>出力ストリームの close 関数

この `close` メンバー関数は、出力ファイルストリームに関連付けられているディスクファイルを閉じます。 すべてのディスク出力を完了するには、ファイルを閉じる必要があります。 必要に応じて、デストラクターによって `ofstream` ファイルが閉じられますが、 `close` 同じストリームオブジェクトの別のファイルを開く必要がある場合は、関数を使用できます。

出力ストリームデストラクターは、コンストラクターまたはメンバー関数がファイルを開いた場合にのみ、ストリームのファイルを自動的に閉じ `open` ます。 既に開いているファイルのファイル記述子をコンストラクターに渡すか、メンバー関数を使用する場合は、 `attach` ファイルを明示的に閉じる必要があります。

## <a name="error-processing-functions"></a><a name="vclrferrorprocessingfunctionsanchor10"></a> エラー処理関数

ストリームへの書き込み中にエラーがないかテストするには、これらのメンバー関数を使用します。

|機能|戻り値|
|--------------|------------------|
|[問題あり](basic-ios-class.md#bad)|**`true`** 回復不可能なエラーがある場合は、を返します。|
|[オーバー](basic-ios-class.md#fail)|回復不可能なエラー、または **`true`** 変換エラーなどの "予期される" 条件が存在する場合、またはファイルが見つからない場合は、を返します。 多くの場合、処理は、ゼロ引数を指定してを呼び出した後に再開でき `clear` ます。|
|[よし](basic-ios-class.md#good)|**`true`** エラー状態 (回復不可能またはそれ以外) が存在せず、ファイルの終わりフラグが設定されていない場合は、を返します。|
|[eof](basic-ios-class.md#eof)|**`true`** ファイルの終わりの条件でを返します。|
|[オフ](basic-ios-class.md#clear)|内部エラー状態を設定します。 既定の引数を指定して呼び出すと、すべてのエラー ビットがクリアされます。|
|rdstate(基本-ios-クラス md # rdstate)|現在のエラー状態を返します。|

**!** 演算子は、関数と同じ関数を実行するためにオーバーロードされ `fail` ます。 したがって次のような式があるとします。

```cpp
if(!cout)...
```

は以下に匹敵します。

```cpp
if(cout.fail())...
```

**Void \* ()** 演算子は、の逆になるようにオーバーロードされます **。** operatorしたがって、式は次のようになります。

```cpp
if(cout)...
```

上の式は、下の式と同等です。

```cpp
if(!cout.fail())...
```

**Void \* ()** 演算子は、 `good` ファイルの終わりをテストしないため、とは等価ではありません。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)
