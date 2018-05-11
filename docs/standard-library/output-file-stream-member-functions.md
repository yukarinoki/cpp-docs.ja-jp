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
ms.openlocfilehash: 7a1cba80b18f94d5a833b238e19be8190a442146
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="output-file-stream-member-functions"></a>出力ファイル ストリームのメンバー関数

出力ストリームのメンバー関数は、マニピュレーターと同等のタイプ、書式設定されていない書き込み操作を実行するタイプ、それ以外はストリーム状態を変更し、同等のマニピュレーターまたは挿入演算子を持たないタイプの 3 つがあります。 書式設定された順次出力の場合、挿入演算子とマニピュレーターのみを使用することがあります。 ランダム アクセス バイナリ ディスク出力の場合、挿入演算子の有無を問わず、他のメンバー関数を使用します。

## <a name="the-open-function-for-output-streams"></a>出力ストリームの open 関数

出力ファイル ストリーム ([ofstream](../standard-library/basic-ofstream-class.md)) を使用するには、コンストラクターまたは **open** 関数で、そのストリームを特定のディスク ファイルに関連付ける必要があります。 **open** 関数を使用する場合、一連のファイルで同じストリーム オブジェクトを再利用することができます。 いずれの場合も、ファイルを記述する引数は同じです。

出力ストリームに関連付けられているファイルを開く場合、通常は **open_mode** フラグを指定します。 `ios` クラスで列挙子として定義されているこれらのフラグを、ビットごとの OR ( &#124; ) 演算子と組み合わせることができます。 列挙子のリストについては、「[ios_base::openmode](../standard-library/ios-base-class.md#openmode)」を参照してください。

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

**write** 関数は、出力ファイル ストリームにメモリ ブロックを書き込みます。 length 引数は、書き込まれるバイト数を指定します。 この例は、出力ファイル ストリームを作成し、`Date` 構造体のバイナリ値をそれに書き込みます。

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

**write** 関数は null 文字に達しても停止しないため、完全なクラス構造が記述されます。 関数は、`char` ポインターと、書き込む文字のカウントという 2 つの引数を取ります。 構造体オブジェクトのアドレスの前にある **char\*** への必須のキャストに注意してください。

## <a name="the-seekp-and-tellp-functions"></a>seekp 関数と tellp 関数

出力ファイル ストリームは、データを次に書き込む位置を指す内部ポインターを保持します。 `seekp` メンバー関数は、このポインターを設定し、それによりランダム アクセス ディスク ファイル出力を提供します。 `tellp` メンバー関数は、ファイル位置を返します。 `seekp` と `tellp` に同等の入力ストリーム関数を使用する例については、「[seekg 関数と tellg 関数](../standard-library/input-stream-member-functions.md)」を参照してください。

## <a name="the-close-function-for-output-streams"></a>出力ストリームの close 関数

**close** メンバー関数は、出力ファイル ストリームに関連付けられているディスク ファイルを閉じます。 すべてのディスク出力を完了するには、ファイルを閉じる必要があります。 必要に応じて、`ofstream` デストラクターによってファイルが閉じられますが、同じストリーム オブジェクトの別のファイルを開く必要がある場合は **close** 関数を使用できます。

出力ストリーム デストラクターが自動的にストリームのファイルを閉じるのは、コンストラクターまたは **open** メンバー関数がファイルを開いた場合のみです。 コンストラクターを既に開いているファイルのファイル記述子に渡すか、**attach** メンバー関数を使用する場合は、ファイルを明示的に閉じる必要があります。

## <a name="vclrferrorprocessingfunctionsanchor10"></a> エラー処理関数

ストリームへの書き込み中にエラーがないかテストするには、これらのメンバー関数を使用します。

|関数|戻り値|
|--------------|------------------|
|[bad](http://msdn.microsoft.com/Library/4038d331-e9c9-48b0-bf49-c6505744469c)|回復不可能なエラーがある場合は **true**。|
|[fail](http://msdn.microsoft.com/Library/619f1b36-1e72-4551-8b48-888ae4e370d2)|回復不可能なエラーがある場合、または変換エラーなどの "予想された" 状態である場合、またはファイルが見つからない場合は **true** を返します。 多くの場合、0 個の引数を指定して **clear** を呼び出した後、処理を再開できます。|
|[good](http://msdn.microsoft.com/Library/77f0aa17-2ae1-48ae-8040-592d301e3972)|エラー条件 (回復不可能かどうかを問わず) がなく、ファイルの終わりフラグが設定されていない場合は **true** を返します。|
|[eof](http://msdn.microsoft.com/Library/3087f631-1268-49cd-86cf-ff4108862329)|ファイルの終わり条件で **true** を返します。|
|[clear](http://msdn.microsoft.com/Library/dc172694-1267-45f8-8f5c-e822e16fc271)|内部エラー状態を設定します。 既定の引数を指定して呼び出すと、すべてのエラー ビットがクリアされます。|
|[rdstate](http://msdn.microsoft.com/Library/e235e4e2-7e95-4777-a160-3938d263dd9c)|現在のエラー状態を返します。|

**!** 同じ機能を実行する演算子をオーバー ロード、**失敗**関数。 したがって次のような式があるとします。

```cpp
if(!cout)...
```

上の式は、下の式と同等です。

```cpp
if(cout.fail())...
```

**Void\*()** と逆の働きをする演算子をオーバー ロード、 **!** 演算子です。したがって次の式

```cpp
if(cout)...
```

上の式は、下の式と同等です。

```cpp
if(!cout.fail())...
```

**void\*()** 演算子は、**good** と同等です。これは、ファイルの終わりをテストしないためです。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)<br/>
