---
title: C++標準ライブラリのヘッダーファイル
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: dc337ef078108d86849aa7b7452512dfb69e6e18
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341127"
---
# <a name="c-standard-library-header-files"></a>C++標準ライブラリのヘッダーファイル

C++標準ライブラリと拡張機能のヘッダーファイル (カテゴリ別)。

## <a name="headers-by-category"></a>カテゴリ別ヘッダー

::: moniker range=">=vs-2017"

| Category | ヘッダー |
| - | - |
| [アルゴリズム](../cpp/algorithms-modern-cpp.md) | algorithm > [、 cstdlib>\<](cstdlib.md)、 [ numeric\<>](numeric.md) [ \<](algorithm.md) |
| アトミック操作 |  atomic ><sup>11</sup> [ \<](atomic.md) |
| C ライブラリラッパー | [ \<](cctype.md) [ \<](cerrno.md) [ \<](cfenv.md)<sup></sup><sup></sup> [ cassert\<>](cassert.md)、 [ ccomplex>11ab、cctype>、ccomplex>、cfenv>11、\<](ccomplex.md) [ \<cfloat >](cfloat.md)、 [ \<cinttypes >](cinttypes.md)<sup>11</sup>、 [ \<ciso646 >](ciso646.md)<sup>b</sup>、 [ \<climits >](climits.md)、 [ \<cfloat >](clocale.md)、 [ \<cmath >](cmath.md) [ 、\<cmath >](csetjmp.md)、 [ \<cmath >](csignal.md)、 [ \<cstdalign が >](cstdalign.md)<sup>11 a b</sup>、 [ \<cstdarg >](cstdarg.md)、 [ \<cstdbool >](cstdbool.md)<sup>11 a b</sup>、 [ \<cstddef >](cstddef.md)、 [ \<cstdint >](cstdint.md)<sup>11</sup>、 [ \<cstdio >](cstdio.md)、 [ \<cstdlib >](cstdlib.md)、 [ cstring\<>](cstring.md)、<sup></sup> [ \<](ctime.md)<sup></sup> [ \<](cuchar.md) [ \<](cwchar.md) [ ctgmath>11ab、ctime>、cuchar>\<](ctgmath.md)11、cwchar >、 [ \<cwctype >](cwctype.md) |
| 概念 | \<概念 ><sup>20</sup> |
| [コンテナー](../cpp/containers-modern-cpp.md) | |
| シーケンスコンテナー | <sup></sup><sup></sup> [ array\<>](array.md)11、 [ deque>、forward_list>11、list>、vector>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md) |
| 順序付けされた連想コンテナー| [\<map>](map.md)、[\<set>](set.md) |
| 順序なしの連想コンテナー | unordered_map ><sup>11</sup>、 [ unordered_set>\<](unordered-set.md)<sup>11</sup> [ \<](unordered-map.md) |
| コンテナーアダプター | [\<queue>](queue.md)、[\<stack>](stack.md) |
| コンテナービュー | \<><sup>20</sup>にスパン |
| [エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md) | <sup></sup> [ cassert\<>](cassert.md) [、 exception\<>](exception.md) [、 stdexcept\<>](stdexcept.md) [、 system_error\<>](system-error.md)11 |
| 一般的なユーティリティ | \<><sup>17</sup>、 [ \<bitset >](bitset.md)、 \<charconv ><sup>17</sup>、 [ \<cstdlib >](cstdlib.md)、 \<実行 ><sup>17</sup>、 [ \<機能 >](functional.md)、 [memory\<>](memory.md)、 \< [ \<](ratio.md)<sup></sup><sup></sup><sup></sup>memory_resource > 17、optional > 17、比率 > 11、scoped_allocator > \< [ \<](scoped-allocator.md) <sup>11</sup><sup></sup><sup></sup> [、組\<>](tuple.md)11 [、 type_traits>11、typeindex>11、utility>、\<](type-traits.md) [ \<](utility.md) [ \<](typeindex.md)<sup></sup>\<バリアント ><sup>17</sup> |
| [I/o と書式設定](../cpp/string-and-i-o-formatting-modern-cpp.md) | [ \<](filesystem.md)<sup></sup><sup></sup> [ \<](cstdio.md) [ \<](fstream.md) [ \<](iomanip.md) [ cinttypes>11、cstdio>、filesystem>17、fstream>\<](cinttypes.md)、iomanip >、 [ ios\<>](ios.md)、 [ iosfwd>、iostream>、istream>、ostream>、sstream>\<](iosfwd.md) [ \<](iostream.md) [ \<](istream.md) [ \<](ostream.md) [ \<](sstream.md)\< [ 、\<streambuf >](streambuf.md)、 [ \<strstream >](strstream.md)<sup>c</sup>、syncstream ><sup>20</sup> |
| 反復子 | [\<iterator>](iterator.md) |
| 言語サポート | \< \<<sup></sup> \< <sup></sup><sup></sup> [ cfloat\<>、climits >](climits.md)、 [ \<codecvt >](codecvt.md)11 a、比較 > 20、コントラクト > 20、 [ \<](cfloat.md)コルーチン ><sup>20</sup>、 [ \<csetjmp >](csetjmp.md)、 [ \<csetjmp >](csignal.md)、 [ \<cstdarg >](cstdarg.md)、 [ \<cstddef >](cstddef.md)、 [ \<cstdint >](cstdint.md) <sup>11</sup><sup></sup> [、 cstdlib\<>](cstdlib.md) [、 exception\<>](exception.md) [、 initializer_list\<>](initializer-list.md)11 [、制限>、\<](limits.md) [ \<新しい >](new.md)、 [ \<typeinfo >](typeinfo.md)、 \<バージョン ><sup>20</sup> |
| ローカリゼーション | [ \<](locale.md) <sup></sup> [ \<](cvt-wbuffer.md) [ clocale\<>、codecvt >](codecvt.md)11 a、cvt/wbuffer >、 [ \<cvt/wbuffer >](cvt-wstring.md)、ロケール > [ \<](clocale.md) |
| 数値演算と数値 | \<ビット ><sup>20</sup>、 [ \<cfenv >](cfenv.md)<sup>11</sup>、 [ \<cmath >](cmath.md)、 [ \<複雑な >](complex.md)、 [ \<cstdlib >](cstdlib.md)、 [ \<制限 >](limits.md)、 [ 数値\<>](numeric.md)、<sup></sup><sup></sup> [ランダム\<>](random.md)11 [、比率>11、valarray>\<](ratio.md) [ \<](valarray.md) |
| [メモリ管理](../cpp/smart-pointers-modern-cpp.md) | <sup></sup><sup></sup> [アロケーター>\<](new.md)、 \< [ \<](scoped-allocator.md) [ memory\<>](memory.md)、memory_resource > 17、new >、scoped_allocator > 11 [ \<](allocators-header.md) |
| マルチスレッド | <sup></sup><sup></sup><sup></sup><sup></sup> [ atomic\<>](atomic.md)11、 [ condition_variable>11、future>11、mutex>11、\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \<shared_mutex >](shared-mutex.md)<sup>14</sup>、 [ \<スレッド >](thread.md)<sup>11</sup> |
| 範囲 | \<範囲 ><sup>20</sup> |
| 正規表現 | regex ><sup>11</sup> [ \<](regex.md) |
| 文字列と文字データ | <sup></sup> [ \<](cwchar.md) [ cctype\<>、cstdlib >](cstdlib.md)、 [ \<cstring >](cstring.md)、 [ \<cuchar >](cuchar.md)11、cwchar >、 [ \<](cctype.md) [ \<cwctype>](cwctype.md) [ 、\<regex >](regex.md)<sup>11</sup>、 [ \<string >](string.md)、 [ \<string_view >](string-view.md)<sup>17</sup> |
| Time | chrono ><sup>11</sup>、 [ ctime\<>](ctime.md) [ \<](chrono.md) |

<sup>11</sup> c++ 11 標準で追加されました。
<sup>14</sup>は c++ 14 標準で追加されました。
<sup>17</sup>は c++ 17 標準で追加されました。
<sup>20</sup>は、ドラフト c++ 20 標準で追加されました。
C++ 17 標準で非推奨<sup>と</sup>されます。
<sup>b</sup>は、c++ 20 標準のドラフトで削除されました。
<sup>c</sup> c++ 98 標準では非推奨とされます。

::: moniker-end

::: moniker range="vs-2015"

|Category|ヘッダー|
|-|-|
|[アルゴリズム](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|C ライブラリラッパー|[\<cassert>](cassert.md)、[\<cctype>](cctype.md)、[\<cerrno>](cerrno.md)、[\<cfenv>](cfenv.md)、[\<cfloat>](cfloat.md)、[\<cinttypes>](cinttypes.md)、[\<ciso646>](ciso646.md)、[\<climits>](climits.md)、[\<clocale>](clocale.md)、[\<cmath>](cmath.md)、[\<csetjmp>](csetjmp.md)、[\<csignal>](csignal.md)、[\<cstdarg>](cstdarg.md)、[\<cstdbool>](cstdbool.md)、[\<cstddef>](cstddef.md)、[\<cstdint>](cstdint.md)、[\<cstdio>](cstdio.md)、[\<cstdlib>](cstdlib.md)、[\<cstring>](cstring.md)、[\<ctgmath>](ctgmath.md)、[\<ctime>](ctime.md)、[\<cwchar>](cwchar.md)、[\<cwctype>](cwctype.md)|
|[コンテナー](../cpp/containers-modern-cpp.md)||
|シーケンスコンテナー|[ array\<>](array.md)、 [ deque>、forward_list>、list>、vector>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md)|
|順序付けされた連想コンテナー| [\<map>](map.md)、[\<set>](set.md)|
|順序なしの連想コンテナー|unordered_map >、 [ \<](unordered-map.md) [ unordered_set>\<](unordered-set.md)|
|アダプターコンテナー|[\<queue>](queue.md)、[\<stack>](stack.md)|
|[エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)|exception > [、 stdexcept>\<](stdexcept.md)、 [ system_error\<>](system-error.md) [ \<](exception.md)|
|[I/o と書式設定](../cpp/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md)、[\<fstream>](fstream.md)、[\<iomanip>](iomanip.md)、[\<ios>](ios.md)、[\<iosfwd>](iosfwd.md)、[\<iostream>](iostream.md)、[\<istream>](istream.md)、[\<ostream>](ostream.md)、[\<sstream>](sstream.md)、[\<streambuf>](streambuf.md)、[\<strstream>](strstream.md)|
|反復子|[\<iterator>](iterator.md)|
|ローカリゼーション|[\<codecvt>](codecvt.md)、[\<cvt/wbuffer>](cvt-wbuffer.md)、[\<cvt/wstring>](cvt-wstring.md)、[\<locale>](locale.md)|
|数値演算と数値|[\<complex>](complex.md)、[\<limits>](limits.md)、[\<numeric>](numeric.md)、[\<random>](random.md)、[\<ratio>](ratio.md)、[\<valarray>](valarray.md)|
|[メモリ管理](../cpp/smart-pointers-modern-cpp.md)|アロケーター > [、 memory\<>](memory.md)、 [ new\<>](new.md)、 [ scoped_allocator\<>](scoped-allocator.md) [ \<](allocators-header.md)|
|マルチスレッド|[ atomic\<>](atomic.md)、 [ condition_variable>、フューチャ>、mutex>、shared_mutex>、thread\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \<](shared-mutex.md) [ \<>](thread.md)|
|その他のユーティリティ|[ \<](initializer-list.md) [ \<](tuple.md) [ bitset\<>、chrono >](chrono.md)、 [ \<関数型 >](functional.md)、initializer_list >、組 >、type_traits [ \<](bitset.md) [ \<>](type-traits.md) [ 、\<typeinfo >](typeinfo.md)、 [ \<typeindex >](typeindex.md)、 [ \<ユーティリティ >](utility.md)|
|文字列と文字データ|regex > [、 string>\<](string.md)、 [ string_view\<>](string-view.md) [ \<](regex.md)

::: moniker-end

## <a name="see-also"></a>関連項目

[ライブラリC++ヘッダーの使用](using-cpp-library-headers.md)\
[C++標準ライブラリ](cpp-standard-library-reference.md)
