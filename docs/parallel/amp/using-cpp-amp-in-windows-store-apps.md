---
description: 詳細については、UWP アプリでの C++ AMP の使用に関するページを参照してください。
title: UWP アプリでの C++ AMP の使用
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 91c7b147ff89a1fe19ebe1b18e465533053542d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314478"
---
# <a name="using-c-amp-in-uwp-apps"></a>UWP アプリでの C++ AMP の使用

ユニバーサル Windows プラットフォーム (UWP) アプリで C++ AMP (C++ Accelerated Massive Parallelism) を使用して、GPU (グラフィックスプロセッシングユニット) やその他の計算アクセラレータで計算を実行できます。 ただし C++ AMP では、Windows ランタイムの型を直接操作するための API が提供されておらず、Windows ランタイムでは C++ AMP のラッパーが提供されません。 Windows ランタイムの型を (独自に作成したコードも含めて) コード内で使用するときは、C++ AMP と互換性のある型に変換する必要があります。

## <a name="performance-considerations"></a>パフォーマンスに関する考慮事項

ユニバーサル Windows プラットフォーム (UWP) アプリを作成するために Visual C++ コンポーネント拡張機能 C++/CX を使用している場合は、C++ AMP で使用されるデータに対して、(たとえば、C スタイルの配列) という形式の古いデータ (POD) 型を使用することをお勧めし `std::vector` ます。 マーシャリングの必要がないため、非 POD 型または Windows RT コンテナーを使用する場合より高いパフォーマンスの実現に役立ちます。.

C ++ AMP カーネルで、この方法で格納されているデータにアクセスするには、`std::vector` または配列記憶域を `concurrency::array_view` でラップし、この配列ビューを `concurrency::parallel_for_each` ループで使用します。

```cpp
// simple vector addition example
std::vector<int> data0(1024, 1);
std::vector<int> data1(1024, 2);
std::vector<int> data_out(data0.size(), 0);

concurrency::array_view<int, 1> av0(data0.size(), data0);
concurrency::array_view<int, 1> av1(data1.size(), data1);
concurrency::array_view<int, 1> av2(data_out.size(), data2);

av2.discard_data();

concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)
    {
        av2[idx] = av0[idx] + av1[idx];
    });
```

## <a name="marshaling-windows-runtime-types"></a>Windows ランタイム型をマーシャリングする

Windows ランタイム Api を使用する場合は、などの Windows ランタイムコンテナーに格納されているデータ、 `Platform::Array<T>^` または **ref** キーワードまたは **value** キーワードを使用して宣言されているクラスや構造体などの複合データ型に C++ AMP を使用することができます。 この場合、C++ AMP でデータを使用できるように特別な作業を行う必要があります。

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform:: Array \<T> ^ (T は POD 型)

`Platform::Array<T>^` を検出した場合に T が POD 型であれば、基となる記憶域に `get` メンバー関数を使用してアクセスすることができます。

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

T が POD 型でない場合に C++ AMP でデータを使用するには、次のセクションで説明する手法を使用します。

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows ランタイム型: ref クラスと value クラス

C++ AMP では、複合データ型がサポートされません。 これには、非 POD 型と、 **ref** キーワードまたは **value** キーワードを使用して宣言された型が含まれます。 サポートされていない型が `restrict(amp)` のコンテキストで使用されている場合、コンパイル時エラーが生成されます。

サポートされない型を検出した場合は、そのデータの必要な部分を `concurrency::array` オブジェクトにコピーできます。 データを C++ AMP で使用できるようにする作業に加え、この手動コピーを行うことも、データの局所性を最大限に高め、使用しないデータがアクセラレータにコピーされないようにする点で、パフォーマンスの向上に役立ちます。 *ステージングアレイ* を使用すると、さらにパフォーマンスを向上させることができます。これは、 `concurrency::array` AMP ランタイムにヒントを提供する特別な形式のです。これは、指定されたアクセラレータのその他の配列との間で頻繁に転送されるように配列を最適化する必要があることを示します。

```cpp
// pixel_color.h
ref class pixel_color sealed
{
public:
    pixel_color(Platform::String^ color_name, int red, int green, int blue)
    {
        name = color_name;
        r = red;
        g = green;
        b = blue;
    }

    property Platform::String^ name;
    property int r;
    property int g;
    property int b;
};

// Some other file

std::vector<pixel_color^> pixels (256);

for (pixel_color ^pixel : pixels)
{
    pixels.push_back(ref new pixel_color("blue", 0, 0, 255));
}

// Create the accelerators
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);

// Create the staging arrays
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);

// Extract data from the complex array of structs into staging arrays.
concurrency::parallel_for(0, 256, [&](int i)
    {
        red_vec[i] = pixels[i]->r;
        blue_vec[i] = pixels[i]->b;
    });

// Array views are still used to copy data to the accelerator
concurrency::array_view<float, 1> av_red(red_vec);
concurrency::array_view<float, 1> av_blue(blue_vec);

// Change all pixels from blue to red.
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)
    {
        av_red[idx] = 255;
        av_blue[idx] = 0;
    });
```

## <a name="see-also"></a>関連項目

[C++ を使用して初めての UWP アプリを作成する](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
