unit Unit1;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, StdCtrls, Buttons, ExtCtrls, Menus, OleCtrls, SHDocVw, ComCtrls,
  Spin, ColorGrd, ExtDlgs;

type
  TForm1 = class(TForm)
    Panel1: TPanel;
    BitBtn1: TBitBtn;
    BitBtn2: TBitBtn;
    BitBtn3: TBitBtn;
    BitBtn4: TBitBtn;
    BitBtn5: TBitBtn;
    BitBtn6: TBitBtn;
    Panel2: TPanel;
    Label1: TLabel;
    Edit1: TEdit;
    BitBtn7: TBitBtn;
    Panel3: TPanel;
    MainMenu1: TMainMenu;
    N1: TMenuItem;
    N2: TMenuItem;
    N3: TMenuItem;
    PageControl1: TPageControl;
    TabSheet1: TTabSheet;
    TabSheet2: TTabSheet;
    TabSheet3: TTabSheet;
    Timer1: TTimer;
    Label2: TLabel;
    Open1: TMenuItem;
    Save1: TMenuItem;
    History1: TMenuItem;
    Exit1: TMenuItem;
    History2: TMenuItem;
    Help1: TMenuItem;
    SourceCode1: TMenuItem;
    Encoding1: TMenuItem;
    extSize1: TMenuItem;
    Search2: TMenuItem;
    Cut1: TMenuItem;
    Copy1: TMenuItem;
    Paste1: TMenuItem;
    SelectAll1: TMenuItem;
    oday1: TMenuItem;
    Yesterday1: TMenuItem;
    N1weekago1: TMenuItem;
    N1monthago1: TMenuItem;
    Properties1: TMenuItem;
    about1: TMenuItem;
    Print1: TMenuItem;
    Page1: TMenuItem;
    Splitter1: TSplitter;
    Image1: TImage;
    Panel4: TPanel;
    Splitter2: TSplitter;
    ColorGrid1: TColorGrid;
    SpinEdit1: TSpinEdit;
    Button1: TButton;
    Button2: TButton;
    SavePictureDialog1: TSavePictureDialog;
    WebBrowser1: TWebBrowser;
    procedure BitBtn1Click(Sender: TObject);
    procedure BitBtn2Click(Sender: TObject);
    procedure BitBtn3Click(Sender: TObject);
    procedure BitBtn4Click(Sender: TObject);
    procedure BitBtn5Click(Sender: TObject);
    procedure BitBtn6Click(Sender: TObject);
    procedure BitBtn7Click(Sender: TObject);
    procedure Edit1Change(Sender: TObject);
    procedure Timer1Timer(Sender: TObject);
    procedure Exit1Click(Sender: TObject);
    procedure Image1MouseMove(Sender: TObject; Shift: TShiftState; X,
      Y: Integer);
    procedure Image1MouseDown(Sender: TObject; Button: TMouseButton;
      Shift: TShiftState; X, Y: Integer);
    procedure ColorGrid1Change(Sender: TObject);
    procedure SpinEdit1Change(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure Button1Click(Sender: TObject);
    procedure Button2Click(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  Form1: TForm1;

implementation

{$R *.dfm}

procedure TForm1.BitBtn1Click(Sender: TObject);
begin
webbrowser1.GoBack;
end;

procedure TForm1.BitBtn2Click(Sender: TObject);
begin
webbrowser1.GoForward;
end;

procedure TForm1.BitBtn3Click(Sender: TObject);
begin
webbrowser1.Stop;
end;

procedure TForm1.BitBtn4Click(Sender: TObject);
begin
webbrowser1.refresh;
end;

procedure TForm1.BitBtn5Click(Sender: TObject);
begin
webbrowser1.GoHome;
end;

procedure TForm1.BitBtn6Click(Sender: TObject);
begin
form1.Close;
end;

procedure TForm1.BitBtn7Click(Sender: TObject);
begin
webbrowser1.GoSearch;
end;

procedure TForm1.Edit1Change(Sender: TObject);
begin
webbrowser1.Navigate(edit1.Text);
end;

procedure TForm1.Timer1Timer(Sender: TObject);
begin
label2.Caption:=timetostr(time);
end;

procedure TForm1.Exit1Click(Sender: TObject);
begin
Form1.Close;
end;

procedure TForm1.Image1MouseMove(Sender: TObject; Shift: TShiftState; X,
  Y: Integer);
begin
 if ssLeft in Shift then Image1.Canvas.LineTo(X,Y); 
end;

procedure TForm1.Image1MouseDown(Sender: TObject; Button: TMouseButton;
  Shift: TShiftState; X, Y: Integer);
begin
Image1.Canvas.MoveTo(X, Y);
with Image1.Canvas do 
case Button of 
mbLeft : MoveTo(X,Y); 
mbRight: FloodFill (X,Y, Pixels [X,Y], fsSurface); 
end;


end;

procedure TForm1.ColorGrid1Change(Sender: TObject);
begin
Image1.Canvas.Pen.Color := ColorGrid1.ForegroundColor; 
Image1.Canvas.Brush.Color:= ColorGrid1.BackgroundColor;

end;

procedure TForm1.SpinEdit1Change(Sender: TObject);
begin
 Image1.Canvas.Pen.Width:=SpinEdit1.Value; 
end;

procedure TForm1.FormCreate(Sender: TObject);
begin
  Image1.Canvas.FillRect(Image1.BoundsRect);
end;

procedure TForm1.Button1Click(Sender: TObject);
begin
image1.Canvas.Brush.Color:=clWhite;
image1.Canvas.FillRect(clientrect);
end;

procedure TForm1.Button2Click(Sender: TObject);
 var
Img:TBitmap;
Region: TRect;
begin
if SavePictureDialog1.Execute then
Img:= TBitmap.Create;
try
Img.Width:= Image1.Width;
Img.Height:= Image1.Height;
Region := Rect(0, 0, Img.Width,Img.Height);
Img.Canvas.CopyRect(Region ,Image1.Canvas, Region );
Img.SaveToFile(SavePictureDialog1.FileName);
finally
Img.Free;
end;
end;
end.

