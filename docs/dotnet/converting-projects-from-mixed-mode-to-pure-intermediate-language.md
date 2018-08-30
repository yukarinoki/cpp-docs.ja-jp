---
title: 純粋な中間言語モードを混在からプロジェクトを変換する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 263a90710d2103c4ea97e6c56da67d676ba7366b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222081"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>混在モードから純粋な中間言語へのプロジェクトの変換

すべてのビジュアルの C++ CLR プロジェクトは、既定では、C ランタイム ライブラリにリンクします。 その結果、ネイティブ コードと共通言語ランタイム (マネージ コード) を対象とするコードを結合するために、これらのプロジェクトは、混合モード アプリケーションとして分類されます。 コンパイル時に、中間言語 (IL) とも呼ばれる Microsoft intermediate language (MSIL) にコンパイルされます。

> [!IMPORTANT]
> Visual Studio 2015 で非推奨とされ、Visual Studio 2017 の作成をサポートできなく **/clr: 純粋な**または **/clr:safe** CLR アプリケーションのコード。 純粋なまたは安全なアセンブリを必要とする場合は、アプリケーションを c# に変換するをお勧めします。

以前のバージョンをサポートする Visual C コンパイラ ツールセットを使用している場合 **/clr: 純粋な**または **/clr:safe**コードを純粋 MSIL に変換するこの手順を使用することができます。

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>混合モード アプリケーションを純粋な中間言語に変換するには

1. リンクを削除、 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)(CRT)。

   1. .Cpp ファイルで、アプリケーションのエントリ ポイントを定義するへのエントリ ポイントを変更`Main()`します。 使用して`Main()`プロジェクトは、CRT にリンクしていないことを示します。

   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、選択**プロパティ**ショートカット メニューのアプリケーションのプロパティ ページを開きます。

   3. **[詳細設定]** のプロジェクト プロパティ ページ、**リンカー**を選択します、**エントリ ポイント**し、入力**Main**このフィールドにします。

   4. コンソール アプリケーションで、**システム**のプロジェクト プロパティ ページ、**リンカー**を選択、**サブシステム**フィールドを変更して**コンソール (/SUBSYSTEM:CONSOLE)** します。

      > [!NOTE]
      > に、Windows フォーム アプリケーションには、このプロパティを設定する必要はありません、**サブシステム**にフィールドが設定されている**Windows (/: WINDOWS サブシステム)** 既定で。

   5. Stdafx.h に、すべてコメント、`#include`ステートメント。 たとえば、コンソール アプリケーション: で

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       - または -

       たとえばでは Windows フォーム アプリケーション。

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Form1.cpp での Windows フォーム アプリケーションをコメント アウト用、 `#include` windows.h を参照するステートメント。 例えば:

      ```cpp
      // #include <windows.h>
      ```

2. Stdafx.h に、次のコードを追加します。

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. すべてのアンマネージ型を削除します。

   構造への参照にアンマネージ型を置き換える、必要に応じて、[システム](https://msdn.microsoft.com/library/system.appdomainmanager.appdomainmanager.aspx)名前空間。 一般的なマネージ型は、次の表のとおりです。

   |構造体|説明|
   |---------------|-----------------|
   |[Boolean](https://msdn.microsoft.com/library/system.boolean\(v=vs.140\).aspx)|ブール値を表します。|
   |[Byte](https://msdn.microsoft.com/library/system.byte\(v=vs.140\).aspx)|8 ビット符号なし整数を表します。|
   |[Char](https://msdn.microsoft.com/library/system.char\(v=vs.140\).aspx)|Unicode 文字を表します。|
   |[DateTime](https://msdn.microsoft.com/library/system.datetime.datetime.aspx)|通常、日付や時刻として表現される瞬間を表します。|
   |[Decimal](https://msdn.microsoft.com/library/system.decimal\(v=vs.140\).aspx)|10 進数を表します。|
   |[Double](https://msdn.microsoft.com/library/system.double\(v=vs.140\).aspx)|倍精度浮動小数点数を表します。|
   |[Guid](https://msdn.microsoft.com/library/system.guid\(v=vs.140\).aspx)|グローバル一意識別子 (GUID) を表します。|
   |[Int16](https://msdn.microsoft.com/library/system.int16\(v=vs.140\).aspx)|16 ビット符号付き整数を表します。|
   |[Int32](https://msdn.microsoft.com/library/system.int32\(v=vs.140\).aspx)|32 ビット符号付き整数を表します。|
   |[Int64](https://msdn.microsoft.com/library/system.int64\(v=vs.140\).aspx)|64 ビット符号付き整数を表します。|
   |[IntPtr](https://msdn.microsoft.com/library/system.intptr\(v=vs.140\).aspx)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|
   |[SByte](https://msdn.microsoft.com/library/system.byte.aspx)|8 ビット符号付き整数を表します。|
   |[Single](https://msdn.microsoft.com/library/system.single.aspx)|単精度浮動小数点数を表します。|
   |[TimeSpan](https://msdn.microsoft.com/library/system.timespan\(v=vs.140\).aspx)|時間間隔を表します。|
   |[UInt16](https://msdn.microsoft.com/library/system.uint16\(v=vs.140\).aspx)|16 ビット符号なし整数を表します。|
   |[UInt32](https://msdn.microsoft.com/library/system.uint32\(v=vs.140\).aspx)|32 ビット符号なし整数を表します。|
   |[UInt64](https://msdn.microsoft.com/library/system.uint64\(v=vs.140\).aspx)|64 ビット符号なし整数を表します。|
   |[UIntPtr](https://msdn.microsoft.com/library/system.uintptr\(v=vs.140\).aspx)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|
   |[void](https://msdn.microsoft.com/library/system.void\(v=vs.140\).aspx)|値を返さないメソッドを示しますメソッドは、void の戻り値の型。|