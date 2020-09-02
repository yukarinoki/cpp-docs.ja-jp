---
title: C++ 標準ライブラリのヘッダーファイル
description: C++ 標準ライブラリのヘッダーファイル (分類済み)
ms.date: 08/31/2020
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: 0bbd67468c1df8b9e7c078f498d19f01f848149c
ms.sourcegitcommit: e58918c45316d799c1952ca7797a85adbcd0c472
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "89281849"
---
# <a name="c-standard-library-header-files"></a>C++ 標準ライブラリのヘッダーファイル

C++ 標準ライブラリと拡張機能のヘッダーファイル (カテゴリ別)。

## <a name="headers-by-category"></a>カテゴリ別ヘッダー

::: moniker range=">=vs-2017"

| カテゴリ | ヘッダー |
| - | - |
| [アルゴリズム](../cpp/algorithms-modern-cpp.md) | [\<algorithm>](algorithm.md), [\<cstdlib>](cstdlib.md), [\<numeric>](numeric.md) |
| アトミック操作 |  [\<atomic>](atomic.md)<sup>個</sup> |
| C ライブラリラッパー | [\<cassert>](cassert.md)、 [\<ccomplex>](ccomplex.md) <sup>11 a b</sup>、 [\<cctype>](cctype.md) 、 [\<cerrno>](cerrno.md) 、 [\<cfenv>](cfenv.md) <sup>11</sup>、 [\<cfloat>](cfloat.md) 、 [\<cinttypes>](cinttypes.md) <sup>11</sup>、 [\<ciso646>](ciso646.md) <sup>b</sup>、、、、、 [\<climits>](climits.md) [\<clocale>](clocale.md) [\<cmath>](cmath.md) [\<csetjmp>](csetjmp.md) [\<csignal>](csignal.md) 、 [\<cstdalign>](cstdalign.md) <sup>11 a b</sup>、 [\<cstdarg>](cstdarg.md) 、 [\<cstdbool>](cstdbool.md) <sup>11 a b</sup>、 [\<cstddef>](cstddef.md) 、 [\<cstdint>](cstdint.md) <sup>11</sup>、 [\<cstdio>](cstdio.md) 、 [\<cstdlib>](cstdlib.md) 、 [\<cstring>](cstring.md) [\<ctgmath>](ctgmath.md) <sup>11 a b</sup>、 [\<ctime>](ctime.md) 、 [\<cuchar>](cuchar.md) <sup>11</sup> [\<cwchar>](cwchar.md) 11、、[\<cwctype>](cwctype.md) |
| 概念 | \<concepts><sup>20@@</sup> |
| [Containers](../cpp/containers-modern-cpp.md) | |
| シーケンスコンテナー | [\<array>](array.md)<sup>11</sup>、 [\<deque>](deque.md) 、 [\<forward_list>](forward-list.md) <sup>11</sup>、 [\<list>](list.md) 、[\<vector>](vector.md) |
| 順序付けされた連想コンテナー| [\<map>](map.md), [\<set>](set.md) |
| 順序なしの連想コンテナー | [\<unordered_map>](unordered-map.md)<sup>11</sup>、 [\<unordered_set>](unordered-set.md) <sup>11</sup> |
| コンテナーアダプター | [\<queue>](queue.md), [\<stack>](stack.md) |
| コンテナービュー | [\<span>](span.md)<sup>20@@</sup> |
| [エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md) | [\<cassert>](cassert.md)、 [\<exception>](exception.md) 、 [\<stdexcept>](stdexcept.md) 、 [\<system_error>](system-error.md) <sup>11</sup> |
| 一般的なユーティリティ | \<any><sup>17</sup>、 [\<bit>](bit.md) <sup>20</sup>、 [\<bitset>](bitset.md) 、 [\<cstdlib>](cstdlib.md) 、 \<execution> <sup>17</sup>、 [\<functional>](functional.md) 、 [\<memory>](memory.md) 、 \<memory_resource> <sup>17</sup>、 \<optional> <sup>17</sup>、 [\<ratio>](ratio.md) <sup>11</sup>、 [\<scoped_allocator>](scoped-allocator.md) <sup>11</sup>、 [\<tuple>](tuple.md) <sup>11</sup>、11、 [\<type_traits>](type-traits.md) <sup>11</sup> [\<typeindex>](typeindex.md) <sup>11</sup>、 [\<utility>](utility.md) \<variant> <sup>17</sup> |
| [I/o と書式設定](../text/string-and-i-o-formatting-modern-cpp.md) | [\<cinttypes>](cinttypes.md)<sup>11</sup>、、17、、、、、、、、、 [\<cstdio>](cstdio.md) [\<filesystem>](filesystem.md) <sup>17</sup> [\<fstream>](fstream.md) [\<iomanip>](iomanip.md) [\<ios>](ios.md) [\<iosfwd>](iosfwd.md) [\<iostream>](iostream.md) [\<istream>](istream.md) [\<ostream>](ostream.md) [\<sstream>](sstream.md) [\<streambuf>](streambuf.md) 、 [\<strstream>](strstream.md) <sup>c</sup>、 \<syncstream> <sup>20</sup> |
| Iterators | [\<iterator>](iterator.md) |
| 言語のサポート | [\<cfloat>](cfloat.md)、 [\<climits>](climits.md) 、 [\<codecvt>](codecvt.md) <sup>11 a</sup>、 \<compare> <sup>20</sup>、 \<contract> <sup>20</sup>、 \<coroutine> <sup>20</sup>、、、、 [\<csetjmp>](csetjmp.md) [\<csignal>](csignal.md) [\<cstdarg>](cstdarg.md) [\<cstddef>](cstddef.md) [\<cstdint>](cstdint.md) <sup>11</sup>、 [\<cstdlib>](cstdlib.md) 、、 [\<exception>](exception.md) [\<initializer_list>](initializer-list.md) <sup>11</sup>、 [\<limits>](limits.md) 、、 [\<new>](new.md) [\<typeinfo>](typeinfo.md) 、 \<version> <sup>20</sup> |
| ローカリゼーション | [\<clocale>](clocale.md)、 [\<codecvt>](codecvt.md) <sup>11 a</sup>、 [\<cvt/wbuffer>](cvt-wbuffer.md) 、 [\<cvt/wstring>](cvt-wstring.md) 、[\<locale>](locale.md) |
| 数値演算と数値 | \<bit><sup>20</sup>、 [\<cfenv>](cfenv.md) <sup>11</sup>、、、、、 [\<cmath>](cmath.md) [\<complex>](complex.md) [\<cstdlib>](cstdlib.md) [\<limits>](limits.md) [\<numeric>](numeric.md) 、 [\<random>](random.md) <sup>11</sup>、 [\<ratio>](ratio.md) <sup>11</sup>、[\<valarray>](valarray.md) |
| [メモリ管理](../cpp/smart-pointers-modern-cpp.md) | [\<allocators>](allocators-header.md)、 [\<memory>](memory.md) 、 \<memory_resource> <sup>17</sup>、 [\<new>](new.md) 、 [\<scoped_allocator>](scoped-allocator.md) <sup>11</sup> |
| マルチスレッド | [\<atomic>](atomic.md)<sup>11</sup>、 [\<condition_variable>](condition-variable.md) <sup>11</sup>、 [\<future>](future.md) <sup>11</sup>、 [\<mutex>](mutex.md) <sup>11</sup>、 [\<shared_mutex>](shared-mutex.md) <sup>14</sup>、 [\<thread>](thread.md) <sup>11</sup> |
| 範囲 | \<ranges><sup>20@@</sup> |
| 正規表現 | [\<regex>](regex.md)<sup>個</sup> |
| 文字列と文字データ | [\<charconv>](charconv.md)<sup>17</sup>、、、、 [\<cctype>](cctype.md) [\<cstdlib>](cstdlib.md) [\<cstring>](cstring.md) [\<cuchar>](cuchar.md) <sup>11</sup>、 [\<cwchar>](cwchar.md) 、 [\<cwctype>](cwctype.md) 、 [\<regex>](regex.md) <sup>11</sup>、 [\<string>](string.md) 、 [\<string_view>](string-view.md) <sup>17</sup> |
| 時間 | [\<chrono>](chrono.md)<sup>11</sup>、 [\<ctime>](ctime.md) |

<sup>11</sup> c++ 11 標準で追加されました。
<sup>14</sup> は c++ 14 標準で追加されました。
<sup>17</sup> は c++ 17 標準で追加されました。
<sup>20</sup> は、ドラフト c++ 20 標準で追加されました。
C++ 17 標準で非推奨<sup>と</sup>されます。
<sup>b</sup> は、c++ 20 標準のドラフトで削除されました。
<sup>c</sup> c++ 98 標準では非推奨とされます。

::: moniker-end

::: moniker range="vs-2015"

|カテゴリ|ヘッダー|
|-|-|
|[アルゴリズム](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|C ライブラリラッパー|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[Containers](../cpp/containers-modern-cpp.md)||
|シーケンスコンテナー|[\<array>](array.md), [\<deque>](deque.md), [\<forward_list>](forward-list.md), [\<list>](list.md), [\<vector>](vector.md)|
|順序付けされた連想コンテナー| [\<map>](map.md), [\<set>](set.md)|
|順序なしの連想コンテナー|[\<unordered_map>](unordered-map.md), [\<unordered_set>](unordered-set.md)|
|アダプターコンテナー|[\<queue>](queue.md), [\<stack>](stack.md)|
|[エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)|[\<exception>](exception.md), [\<stdexcept>](stdexcept.md), [\<system_error>](system-error.md)|
|[I/o と書式設定](../text/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|Iterators|[\<iterator>](iterator.md)|
|ローカリゼーション|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|数値演算と数値|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[メモリ管理](../cpp/smart-pointers-modern-cpp.md)|[\<allocators>](allocators-header.md), [\<memory>](memory.md), [\<new>](new.md), [\<scoped_allocator>](scoped-allocator.md)|
|マルチスレッド|[\<atomic>](atomic.md), [\<condition_variable>](condition-variable.md), [\<future>](future.md), [\<mutex>](mutex.md), [\<shared_mutex>](shared-mutex.md), [\<thread>](thread.md)|
|その他のユーティリティ|[\<bitset>](bitset.md), [\<chrono>](chrono.md), [\<functional>](functional.md), [\<initializer_list>](initializer-list.md), [\<tuple>](tuple.md), [\<type_traits>](type-traits.md), [\<typeinfo>](typeinfo.md), [\<typeindex>](typeindex.md), [\<utility>](utility.md)|
|文字列と文字データ|[\<regex>](regex.md), [\<string>](string.md), [\<string_view>](string-view.md)

::: moniker-end

## <a name="see-also"></a>関連項目

[C++ ライブラリヘッダーの使用](using-cpp-library-headers.md)\
[C++ 標準ライブラリ](cpp-standard-library-reference.md)
