---
title: _ITERATOR_DEBUG_LEVEL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7219ed039e77d0857151c54e73a03a0d1f6a3f5e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864139"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

`_ITERATOR_DEBUG_LEVEL` マクロは、[チェックを行う反復子](../standard-library/checked-iterators.md)および[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)が有効かどうかを制御します。 このマクロは、以前の `_SECURE_SCL` および `_HAS_ITERATOR_DEBUGGING` マクロを置き換え、組み合わせたものです。

## <a name="macro-values"></a>マクロの値

`_ITERATOR_DEBUG_LEVEL` マクロの有効値を次の表に示します。

|コンパイル モード|マクロの値|説明|
|----------------------|----------------|-----------------|
|**Debug**|||
||0|チェックを行う反復子を無効にし、反復子のデバッグを無効にします。|
||1|チェックを行う反復子を有効にし、反復子のデバッグを無効にします。|
||2 (既定値)|反復子のデバッグを有効にします。チェックを行う反復子は関連しません。|
|**Release**|||
||0 (既定値)|チェックを行う反復子を無効にします。|
||1|チェックを行う反復子を有効にします。反復子のデバッグは関連しません。|

リリース モードでは、`_ITERATOR_DEBUG_LEVEL` に 2 を指定するとコンパイラはエラーを生成します。

## <a name="remarks"></a>コメント

`_ITERATOR_DEBUG_LEVEL` マクロは、[チェックを行う反復子](../standard-library/checked-iterators.md)が有効かどうか、およびデバッグ モードで[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)が有効かどうかを制御します。 `_ITERATOR_DEBUG_LEVEL` が 1 または 2 と定義されている場合、チェックを行う反復子は、コンテナーの境界が上書きされないようにします。 `_ITERATOR_DEBUG_LEVEL` が 0 の場合、反復子はチェックされません。 `_ITERATOR_DEBUG_LEVEL` が 1 と定義されている場合、反復子の安全でない使用によってランタイム エラーが発生し、プログラムが終了します。 `_ITERATOR_DEBUG_LEVEL` が 2 と定義されている場合、反復子の安全でない使用によってアサートが発生し、ランタイム エラー ダイアログによってデバッガーに侵入できます。

`_ITERATOR_DEBUG_LEVEL` マクロでは、`_SECURE_SCL` および `_HAS_ITERATOR_DEBUGGING` マクロと同様の機能がサポートされるため、特定の状況で使用するマクロおよびマクロ値を判断できない場合があります。 混乱を回避するために、`_ITERATOR_DEBUG_LEVEL` マクロのみを使用することをお勧めします。 次の表では、既存のコードの `_SECURE_SCL` および `_HAS_ITERATOR_DEBUGGING` のさまざまな値に使用する `_ITERATOR_DEBUG_LEVEL` マクロの同等の値を示します。

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (リリースの既定値)|0 (無効)|0 (無効)|
|1|1 (有効)|0 (無効)|
|2 (デバッグの既定値)|(関連性なし)|1 (デバッグ モードで有効)|

チェックを行う反復子に関する警告を無効にする方法の詳細については、「[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。

### <a name="example"></a>例

`_ITERATOR_DEBUG_LEVEL` マクロの値を指定するには、[/D](../build/reference/d-preprocessor-definitions.md) コンパイラ オプションを使用して、コマンド ラインで定義するか、または C++ 標準ライブラリ ヘッダーがソース ファイルに含まれる前に `#define` を使用します。 たとえば、コマンド ラインで、*sample.cpp* をデバッグ モードでコンパイルし、反復子のデバッグのサポートを使用するには、`_ITERATOR_DEBUG_LEVEL` マクロ定義を指定します。

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

ソース ファイルで、反復子を定義する標準ライブラリ ヘッダーの前にマクロを指定します。

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>関連項目

[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
