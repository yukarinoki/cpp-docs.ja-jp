---
description: 詳細については、「C++ 標準ライブラリのスレッドセーフ」を参照してください。
title: C++ 標準ライブラリ内のスレッド セーフ
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: 21b4575a217182ef90f8ee506064aab868b9cda9
ms.sourcegitcommit: a89eac9acdbd54a181e3bd5d5bc71a3ef3c1abca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "106506079"
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ 標準ライブラリ内のスレッド セーフ

次のスレッド セーフの規則は C++ 標準ライブラリのすべてのクラスに適用されます。これには、次に示すように `shared_ptr` が含まれます。  より強力な保証が提供されることがあります。たとえば、次に示すような標準の iostream オブジェクトや、のようなマルチスレッド用の型などがあり [`<atomic>`](../standard-library/atomic.md) ます。

オブジェクトは、複数のスレッドからの読み取りに対してスレッド セーフです。 たとえば、オブジェクト A が指定された場合、スレッド 1 とスレッド 2 から A の同時読み取りを安全に行うことができます。

あるオブジェクトに対して 1 つのスレッドが書き込みを行っている場合、同じスレッドまたは別のスレッドでのそのオブジェクトに対する読み取りと書き込みはすべて保護される必要があります。 たとえば、オブジェクト A が指定され、スレッド 1 が A に書き込みを行っている場合、スレッド 2 で A の読み取りや書き取りを行えないようにする必要があります。

別のスレッドが同じ型の別のインスタンスに対して読み取りまたは書き込みを行っている場合でも、型の1つのインスタンスに対して読み取りと書き込みを安全に行うことができます。 たとえば、同じ型のオブジェクト A と B が指定されている場合、がスレッド1で書き込まれ、B がスレッド2で読み取られると、安全です。

## <a name="shared_ptr"></a>shared_ptr

[`shared_ptr`](../standard-library/shared-ptr-class.md)オブジェクトが所有権を共有するコピーであっても、複数のスレッドが同時に異なるオブジェクトの読み取りと書き込みを行うことができます。

## <a name="iostream"></a>iostream

標準の iostream オブジェクト、、、、、、 `cin` `cout` `cerr` 、およびは、 `clog` `wcin` `wcout` `wcerr` `wclog` 他のクラスと同じ規則に従いますが、例外として、複数のスレッドからオブジェクトに安全に書き込むことができます。 たとえば、スレッド1はスレッド2と同時にに書き込むことができ [`cout`](../standard-library/iostream.md#cout) ます。 ただし、2 つのスレッドからの出力が混ざる可能性があります。

> [!NOTE]
> ストリーム バッファーからの読み取りは、読み取り操作とは見なされません。 代わりに、クラスの状態が変更されるため、書き込み操作と見なされます。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)
