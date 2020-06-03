---
title: PgoAutoSweep
ms.date: 07/02/2019
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 57bcd1b2e9f0a3312867c4373fd1e50bcf91576e
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552244"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` では、現在のプロファイル カウンター情報がファイルに保存され、その後、カウンターがリセットされます。 ガイド付き最適化のプロファイル トレーニング中にこの関数を使用すると、最適化ビルドで後で使用するため、実行中のプログラムから `.pgc` ファイルにすべてのプロファイル データが書き込まれます。

## <a name="syntax"></a>構文

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>パラメーター

*name*<br/>
保存済み `.pgc` ファイルを識別する文字列。

## <a name="remarks"></a>Remarks

アプリケーションから `PgoAutoSweep` を呼び出し、アプリケーション実行中、任意の時点でプロファイル データを保存し、リセットできます。 インストルメント化されたビルドでは、`PgoAutoSweep` によって現在のプロファイル データがキャプチャされ、それがファイルに保存され、プロファイル カウンターがリセットされます。 実行可能ファイルの特定の位置で [pgosweep](pgosweep.md) コマンドを呼び出すことと同じです。 最適化されたビルドでは、`PgoAutoSweep` は操作なしです。

保存されたプロファイル カウンター データは *base_name*-*name*!*value*.pgc という名前のファイルに保存されます。*base_name* は実行可能ファイルの基礎名です。*name* は `PgoAutoSweep` に渡されたパラメーターです。*value* は一意の値であり、ファイル名の競合を回避するため、通常は単調に数値を上げます。

`PgoAutoSweep` によって作成された `.pgc` ファイルは、最適化された実行可能ファイルを作成するため、`.pgd` ファイルに結合する必要があります。 [pgomgr](pgomgr.md) コマンドを使用し、結合できます。

[/USEPROFILE](reference/useprofile.md) リンカー オプションに **PGD=** _filename_ 引数を使用するか、非推奨の **/PGD** リンカー オプションを使用することで、最適化ビルド中、結合した `.pgd` ファイルの名前をリンカーに渡すことができます。 *base_name*.pgd という名前のファイルに `.pgc` ファイルを結合した場合、リンカーによって既定でこのファイル名が選択されるため、コマンド ラインにファイル名を指定する必要がありません。

`PgoAutoSweep` 関数は、インストルメント化されたビルドの作成時に指定されたスレッドセーフの設定を保持します。 既定の設定を使用するか、[/GENPROFILE または /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) リンカー オプションに **NOEXACT** 引数を指定する場合、`PgoAutoSweep` の呼び出しはスレッドセーフではありません。 **EXACT** 引数により、インストルメント化された実行可能ファイルはスレッドセーフになり、精度が上がり、速度が下がります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

実行可能ファイルでは、リンクされているライブラリに pgobootrun.lib ファイルを含める必要があります。 このファイルは、Visual Studio インストールの、サポートされているアーキテクチャ別の VC ライブラリ ディレクトリに含まれます。

## <a name="example"></a>例

次の例では、`PgoAutoSweep` を使用し、実行中、異なる時点で 2 つの `.pgc` ファイルが作成されます。 最初のファイルには、`count` が 3 に等しくなるまでのランタイム動作を説明するデータが含まれます。2 つ目のファイルには、この時点の後、アプリケーションの終了直前までに収集されたデータが含まれます。

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

開発者コマンド プロンプトでは、このコマンドを利用し、コードをオブジェクト ファイルにコンパイルします。

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

次に、このコマンドを利用し、トレーニング用にインストルメント化されたビルドが生成されます。

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

インストルメント化された実行可能ファイルを実行し、トレーニング データをキャプチャします。 `PgoAutoSweep` の呼び出しで出力されたデータは、pgoautosweep-func1!1.pgc という名前のファイルと pgoautosweep-func2!1.pgc という名前のファイルに保存されます。 プログラムを実行すると、その出力は次のようになります。

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

**pgomgr** コマンドを実行し、プロファイル トレーニング データベースに保存済みデータを結合します。

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

このコマンドの出力は次のようになります。

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

これで、このトレーニング データを使用し、最適化されたビルドを生成できるようになりました。 このコマンドを使用し、最適化された実行可能ファイルをビルドします。

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
