---
description: '詳細については、次を参照してください: テクニカルノート 59: MFC の MBCS/Unicode 変換マクロの使用'
title: 'テクニカルノート 59: MFC MBCS-Unicode 変換マクロの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
ms.openlocfilehash: c1b767a8d90f2c788a15c9e880056206e7d1326a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214768"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>テクニカル ノート 59: MFC の MBCS/Unicode 変換マクロの使用

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、AFXPRIV.H で定義されている MBCS/Unicode 変換にマクロを使用する方法について説明します。 これらのマクロは、アプリケーションが OLE API を直接処理する場合や、何らかの理由で、多くの場合、Unicode と MBCS を変換する必要がある場合に最も役立ちます。

## <a name="overview"></a>概要

MFC 3.x では、OLE インターフェイスが呼び出されたときに Unicode と MBCS を自動的に変換するために、特殊な DLL (MFCANS32.DLL) が使用されていました。 この DLL は、ole Api とインターフェイスが常に Unicode (Macintosh を除く) であっても、ole アプリケーションを MBCS として記述することを許可する、ほぼ透過的なレイヤーでした。 このレイヤーは便利で、Win16 から Win32 (MFC、Microsoft Word、Microsoft Excel、および VBA) から Win32 に迅速に移植することができましたが、パフォーマンスが大幅に低下することがありました。 このため、MFC 4.x は、この DLL を使用せず、代わりに Unicode OLE インターフェイスと直接対話します。 これを行うには、OLE インターフェイスを呼び出すときに、MFC で Unicode に変換する必要があります。また、OLE インターフェイスを実装するときは、多くの場合、Unicode から MBCS に変換する必要があります。 これを効率的かつ簡単に処理できるように、多くのマクロが作成され、この変換が容易になりました。

このようなマクロのセットを作成するうえで最も大きな課題の1つは、メモリの割り当てです。 文字列は変換できないため、変換された結果を保持する新しいメモリを割り当てる必要があります。 これは、次のようなコードを使用して行われた可能性があります。

```
// we want to convert an MBCS string in lpszA
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];
MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string
delete[] lpszW;
```

このアプローチはいくつかの問題です。 主な問題は、記述、テスト、およびデバッグのためのコードが多数あることです。 単純な関数呼び出しであったものは、はるかに複雑になりました。 また、そのためには、実行時に大きなオーバーヘッドが発生します。 メモリは、ヒープ上に割り当てられ、変換が完了するたびに解放される必要があります。 最後に、Unicode および Macintosh ビルドの場合、上記のコードで適切なを追加する必要があり `#ifdefs` ます (この変換を行う必要はありません)。

このソリューションでは、いくつかのマクロを作成します。 1) さまざまなプラットフォームの違いをマスクします。 2) 効率的なメモリ割り当てスキームを使用し、3) 既存のソースコードに簡単に挿入できます。 定義の1つの例を次に示します。

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

上記のコードの代わりにこのマクロを使用すると、非常に簡単になります。

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

変換が必要な場合の追加の呼び出しがありますが、マクロの使用は単純で効果的です。

各マクロの実装では、_alloca () 関数を使用して、ヒープではなくスタックからメモリを割り当てます。 スタックからメモリを割り当てる方が、ヒープにメモリを割り当てるよりもはるかに高速で、関数が終了したときにメモリが自動的に解放されます。 また、マクロは (または) を複数回呼び出すことを回避し `MultiByteToWideChar` `WideCharToMultiByte` ます。 これを行うには、必要な量よりも少し多くのメモリを割り当てます。 MBC は最大で1つの **wchar** に変換され、 **wchar** ごとに最大2つの MBC バイトを持つことがわかっています。 必要以上に多くのものを割り当てることによって、変換を処理するのに十分なことは、変換関数への2回目の呼び出しでは回避されます。 ヘルパー関数を呼び出すと、 `AfxA2Whelper` 変換を実行するために実行する必要がある引数プッシュの数が減ります (これにより、コードが直接呼び出された場合よりも小さなコードになり `MultiByteToWideChar` ます)。

マクロに一時的な長さを格納するための領域を確保するには、変換マクロを使用する各関数でこれを行う _convert という名前のローカル変数を宣言する必要があります。 この操作を行うには、例で示したように USES_CONVERSION マクロを呼び出します。

一般的な変換マクロと OLE 固有のマクロの両方があります。 これらの2つの異なるマクロセットについて以下に説明します。 すべてのマクロは AFXPRIV.H に格納されています。

## <a name="generic-conversion-macros"></a>汎用変換マクロ

一般的な変換マクロは、基になるメカニズムを形成します。 前のセクション「A2W」で示したマクロの例と実装は、このような "generic" マクロの1つです。 特に OLE とは関係ありません。 汎用マクロのセットを次に示します。

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

テキスト変換を行うだけでなく、、、 `TEXTMETRIC` `DEVMODE` `BSTR` 、および OLE に割り当てられた文字列を変換するためのマクロとヘルパー関数もあります。 これらのマクロについては、この説明の範囲を超えています。 AFXPRIV.H を参照してください。これらのマクロの詳細については、「」を参照してください。

## <a name="ole-conversion-macros"></a>OLE 変換マクロ

OLE 変換マクロは、 **OLESTR** 文字を期待する関数の処理専用に設計されています。 OLE ヘッダーを調べると、 **LPCOLESTR** と **OLECHAR** への多くの参照が表示されます。 これらの型は、プラットフォームに固有ではない方法で OLE インターフェイスで使用される文字の種類を参照するために使用されます。 **OLECHAR** は、Win **`char`** および Macintosh プラットフォームと Win32 の **WCHAR** でにマップされます。

MFC コード内の **#ifdef** ディレクティブの数を最小限に抑えるために、OLE 文字列が関係する変換ごとに同様のマクロを使用します。 最もよく使用されるマクロは次のとおりです。

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

ここでも、TEXTMETRIC、DEVMODE、BSTR、および OLE に割り当てられた文字列を実行するための同様のマクロがあります。 AFXPRIV.H を参照してください。詳細については、「」を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

マクロは、短いループでは使用しないでください。 たとえば、次のような種類のコードを記述しないとします。

```cpp
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

上記のコードでは、文字列の内容に応じて、スタックにメガバイトのメモリを割り当てることができます `lpsz` 。 また、ループの反復ごとに文字列を変換するのに時間がかかります。 代わりに、このような定数変換をループから移動します。

```cpp
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

文字列が定数でない場合は、メソッド呼び出しを関数にカプセル化します。 これにより、毎回変換バッファーが解放されます。 次に例を示します。

```cpp
void CallSomeMethod(int ii, LPCTSTR lpsz)
{
    USES_CONVERSION;
    pI->SomeMethod(ii, T2COLE(lpsz));

}

void MuchBetterIterateCode2(LPCTSTR* lpszArray)
{
    for (int ii = 0; ii <10000; ii++)
    CallSomeMethod(ii, lpszArray[ii]);

}
```

戻り値が返される前にデータのコピーを作成することを意味しない限り、いずれかのマクロの結果を返すことはありません。 たとえば、次のコードは正しくありません。

```
LPTSTR BadConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // bad! returning alloca memory
}
```

上記のコードは、戻り値を値をコピーする値に変更することによって解決できます。

```
CString BetterConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // CString makes copy
}
```

マクロは簡単に使用でき、コードに簡単に挿入できますが、上記の警告からわかるように、使用する際には注意が必要です。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
