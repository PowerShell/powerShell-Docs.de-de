---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Erstellen einer grafischen Datumsauswahl
ms.assetid: c1cb722c-41e9-4baa-be83-59b4653222e9
ms.openlocfilehash: 6dd43a3b1f4c67633ad1755de3db88eb8c6772c8
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53401148"
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="506f2-103">Erstellen einer grafischen Datumsauswahl</span><span class="sxs-lookup"><span data-stu-id="506f2-103">Creating a Graphical Date Picker</span></span>

<span data-ttu-id="506f2-104">Verwenden Sie Windows PowerShell 3.0 und neuere Versionen, um ein Formular mit einem grafischen Kalendersteuerelement zu erstellen, mit dem Benutzer einen Tag des Monats auswählen können.</span><span class="sxs-lookup"><span data-stu-id="506f2-104">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="506f2-105">Erstellen eines grafischen Steuerelements für die Datumsauswahl</span><span class="sxs-lookup"><span data-stu-id="506f2-105">Create a graphical date-picker control</span></span>

<span data-ttu-id="506f2-106">Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).</span><span class="sxs-lookup"><span data-stu-id="506f2-106">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form

$form.Text = 'Select a Date'
$form.Size = New-Object Drawing.Size @(243,230)
$form.StartPosition = 'CenterScreen'

$calendar = New-Object System.Windows.Forms.MonthCalendar
$calendar.ShowTodayCircle = $false
$calendar.MaxSelectionCount = 1
$form.Controls.Add($calendar)

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(38,165)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(113,165)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

<span data-ttu-id="506f2-107">Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms.**</span><span class="sxs-lookup"><span data-stu-id="506f2-107">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="506f2-108">Sie starten dann eine neue Instanz der .NET Framework-Klasse **Windows.Forms.Form**. Diese stellt ein leeres Formular oder Fenster bereit, in das Sie Steuerelemente einfügen können.</span><span class="sxs-lookup"><span data-stu-id="506f2-108">You then start a new instance of the .NET Framework class **Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object Windows.Forms.Form
```

<span data-ttu-id="506f2-109">Nachdem Sie eine Instanz der Formularklasse erstellt haben, ordnen Sie drei Eigenschaften dieser Klasse Werte zu.</span><span class="sxs-lookup"><span data-stu-id="506f2-109">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="506f2-110">**Text.**</span><span class="sxs-lookup"><span data-stu-id="506f2-110">**Text.**</span></span> <span data-ttu-id="506f2-111">Dies wird der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="506f2-111">This becomes the title of the window.</span></span>

- <span data-ttu-id="506f2-112">**Size.**</span><span class="sxs-lookup"><span data-stu-id="506f2-112">**Size.**</span></span> <span data-ttu-id="506f2-113">Dies ist die Größe des Formulars, in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="506f2-113">This is the size of the form, in pixels.</span></span> <span data-ttu-id="506f2-114">Dieses Skript erstellt ein Formular, das 243 Pixel breit und 230 Pixel hoch ist.</span><span class="sxs-lookup"><span data-stu-id="506f2-114">The preceding script creates a form that’s 243 pixels wide by 230 pixels tall.</span></span>

- <span data-ttu-id="506f2-115">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="506f2-115">**StartingPosition.**</span></span> <span data-ttu-id="506f2-116">Für diese optionale Eigenschaft ist im Skript oben **CenterScreen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="506f2-116">This optional property is set to **CenterScreen** in the preceding script.</span></span> <span data-ttu-id="506f2-117">Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Stelle aus, wenn das Formular geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="506f2-117">If you don’t add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="506f2-118">Durch Festlegen der **StartingPosition** auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="506f2-118">By setting the **StartingPosition** to **CenterScreen**, you’re automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Date'
$form.Size = New-Object Drawing.Size @(243,230)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="506f2-119">Als Nächstes erstellen Sie in Ihrem Formular ein Kalendersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="506f2-119">Next, create and then add a calendar control in your form.</span></span> <span data-ttu-id="506f2-120">In diesem Beispiel wird der aktuelle Tag nicht hervorgehoben oder markiert.</span><span class="sxs-lookup"><span data-stu-id="506f2-120">In this example, the current day is not highlighted or circled.</span></span> <span data-ttu-id="506f2-121">Benutzer können immer nur einen Tag im Kalender auswählen.</span><span class="sxs-lookup"><span data-stu-id="506f2-121">Users can select only one day on the calendar at one time.</span></span>

```powershell
$calendar = New-Object System.Windows.Forms.MonthCalendar
$calendar.ShowTodayCircle = $false
$calendar.MaxSelectionCount = 1
$form.Controls.Add($calendar)
```

<span data-ttu-id="506f2-122">Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="506f2-122">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="506f2-123">Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest.</span><span class="sxs-lookup"><span data-stu-id="506f2-123">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="506f2-124">In diesem Beispiel wird als Position der Schaltfläche 165 Pixel vom oberen Rand des Formulars und 38 Pixel vom linken Rand entfernt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="506f2-124">In this example, the button position is 165 pixels from the form’s top edge, and 38 pixels from the left edge.</span></span> <span data-ttu-id="506f2-125">Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel.</span><span class="sxs-lookup"><span data-stu-id="506f2-125">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="506f2-126">Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.</span><span class="sxs-lookup"><span data-stu-id="506f2-126">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(38,165)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="506f2-127">In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="506f2-127">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="506f2-128">Die Position der Schaltfläche **Abbrechen** ist 165 Pixel vom oberen Rand und 113 Pixel vom linken Rand des Fensters entfernt.</span><span class="sxs-lookup"><span data-stu-id="506f2-128">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(113,165)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="506f2-129">Legen Sie die Eigenschaft **Topmost** auf **$true** fest, um zu erzwingen, dass das Fenster über anderen geöffneten Fenstern und Dialogfeldern geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="506f2-129">Set the **Topmost** property to **$true** to force the window to open atop other open windows and dialog boxes.</span></span>

```powershell
$form.Topmost = $true
```

<span data-ttu-id="506f2-130">Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="506f2-130">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="506f2-131">Abschließend weist der Code im Block **If** Windows an, was mit dem Formular geschehen soll, wenn Benutzer einen Tag im Kalender auswählen und anschließend auf die Schaltfläche **OK** klicken oder die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="506f2-131">Finally, the code inside the **If** block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span> <span data-ttu-id="506f2-132">Windows PowerShell zeigt den Benutzern das ausgewählte Datum an.</span><span class="sxs-lookup"><span data-stu-id="506f2-132">Windows PowerShell displays the selected date to users.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="506f2-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="506f2-133">See Also</span></span>

- [<span data-ttu-id="506f2-134">Hey Scripting Guy: Warum funktionieren diese PowerShell GUI-Beispiele nicht?</span><span class="sxs-lookup"><span data-stu-id="506f2-134">Hey Scripting Guy:  Why don’t these PowerShell GUI examples work?</span></span>](https://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="506f2-135">GitHub Winformsexampleupdates von Dave Wyatt</span><span class="sxs-lookup"><span data-stu-id="506f2-135">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [<span data-ttu-id="506f2-136">Windows PowerShell-Tipp der Woche: Erstellen einer grafischen Datumsauswahl</span><span class="sxs-lookup"><span data-stu-id="506f2-136">Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker</span></span>](https://technet.microsoft.com/library/ff730942.aspx)