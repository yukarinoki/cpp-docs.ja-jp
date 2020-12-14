---
description: 詳細については、「Stream とは」を参照してください。
title: ストリームとは何か
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
ms.openlocfilehash: 3786fe05f25949129c1bce63bdbbd73a16209475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187781"
---
# <a name="what-a-stream-is"></a>ストリームとは何か

C と同じように、C++ には組み込み入出力機能がありません。 ただし、すべての C++ コンパイラには、iostream クラスと呼ばれる、体系的でオブジェクト指向の I/O パッケージがバンドルされています。 ストリームは、iostream クラスの中心となる概念です。 ストリーム オブジェクトは、バイトのソースおよび宛先として機能するスマート ファイルと考えることができます。 ストリームの特性は、ストリームのクラスによって、およびカスタマイズされた挿入演算子と抽出演算子によって決まります。

ディスク オペレーティング システムは、デバイス ドライバーを介して、キーボード、画面、プリンター、および通信ポートを、拡張ファイルとして処理します。 iostream クラスは、これらの拡張ファイルとやり取りします。 組み込みクラスでは、ディスク I/O と同じ構文でメモリからの読み取りとメモリへの書き込みをサポートしているため、ストリーム クラスを簡単に派生させることができます。

## <a name="in-this-section"></a>このセクションの内容

[入出力の代替手段](../standard-library/input-output-alternatives.md)

## <a name="see-also"></a>関連項目

[iostream プログラミング](../standard-library/iostream-programming.md)
