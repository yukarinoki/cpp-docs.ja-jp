---
description: 詳細については、「CLR 統合 (C++/CX)」を参照してください。
title: CLR 統合 (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: ae335168ee456f0461154ab48e9d92325fdc599b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190238"
---
# <a name="clr-integration-ccx"></a>CLR 統合 (C++/CX)

一部の Windows ランタイム型は、C++/CX および共通言語ランタイム (CLR) に基づく言語で特別な処理を受け取ります。 この記事では、1 つの言語のいくつかの型から別の言語へのマップの仕組みについて説明します。 たとえば、CLR は Windows.Foundation.IVector を System.Collections.IList へ、Windows.Foundation.IMap を System.Collections.IDictionary へ、というようにマップします。 同様に、C++/CX は、Platform::D delegate や Platform:: String などの型を特別にマップします。

## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows ランタイムの C++/CX へのマッピング

C++/CX によって Windows メタデータ (winmd) ファイルが読み込まれると、コンパイラは、共通の Windows ランタイム名前空間および型を C++/CX 名前空間および型に自動的にマップします。 たとえば、数値 Windows ランタイム型はに `UInt32` 自動的にマップされ `default::uint32` ます。

C++/CX は、他のいくつかの Windows ランタイム型を **Platform** 名前空間にマップします。 たとえば、読み取り専用の Unicode テキスト文字列を表す **Windows:: Foundation** hstring ハンドルは、C++/cx クラスにマップされ `Platform::String` ます。 Windows ランタイム操作がエラー HRESULT を返すと、C++/CX にマップさ `Platform::Exception` れます。

C++/CX では、Windows ランタイム名前空間の特定の型をマップして、型の機能を強化することもできます。 これらの型については、C++/CX では、C++ に固有のヘルパーコンストラクターとメソッドが提供され、型の標準の winmd ファイルでは使用できません。

新しいコンストラクターとヘルパー メソッドをサポートしている値構造体を次の一覧に示します。 構造体の初期化リストを使用するコードを既に作成済みの場合、新たに追加されたコンストラクターを使用するように変更してください。

**Windows:: Foundation**

- ポイント

- Rect

- サイズ

**Windows:: UI**

- Color

**Windows:: UI:: Xaml**

- CornerRadius

- Duration

- GridLength

- 太さ

**Windows::UI::Xaml::Interop**

- TypeName

**Windows:: UI:: Xaml:: Media**

- Matrix

**Windows:: UI:: Xaml:: Media:: Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>CLR を C++/CX にマップする

Microsoft C++ または C# コンパイラが winmd ファイルを読み取ると、メタデータファイル内の特定の型が適切な C++/CX または CLR 型に自動的にマップされます。 たとえば、CLR では、IVector \<T> インターフェイスは IList にマップされ \<T> ます。 しかし、C++/CX では、IVector \<T> インターフェイスは別の型にマップされません。

Windows ランタイムの IReference \<T> は、.net で Nullable にマップさ \<T> れます。

## <a name="see-also"></a>関連項目

[他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)
