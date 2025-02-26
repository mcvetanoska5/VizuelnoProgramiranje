ОПИС НА ПРОБЛЕМОТ

Ние направивме апликација со чија помош се решаваат математички задачи за деца. На самиот почеток се отвара почетната форма на која може да се избере каков тип на задачи сакате да решавате.
Има избор за решавање на математички задачи со операции и решавање на задачи со геометриски форми. ![image](https://github.com/user-attachments/assets/aeb664b4-977e-4f10-9f78-dc1fcaa3621b)
 Со клик на копчето Guessing shapes се отвара форма за решавање на задачи со геометриски форми. ![image](https://github.com/user-attachments/assets/d1cc0c60-f7dd-4ef6-999e-8d2f60c20a09)
 Има дадена геометриска форма, а во празното поле таа треба да се погодува. Доколку се погоди на екран се испишува Correct и се генерира друга форма. ![image](https://github.com/user-attachments/assets/189cfd04-1bfe-42dc-ba60-3f8f57c74102)
 ![image](https://github.com/user-attachments/assets/36f09c8c-ac9a-45aa-a610-1a411681ca67)
 Доколку формата не се погоди на екран се испишува Incorrect, а бројот на обиди се намалува за 1, и доколку стигне до 0 на екран се појавува MessageBox со порака дека сме изгубиле и дали сакаме нова игра. Ако кликнеме Yes, ќе почне нова игра, а со клик на копчето No, формата ќе се затвори. ![image](https://github.com/user-attachments/assets/823ca952-1def-476f-a5bc-5e1f1e634d57)
 ![image](https://github.com/user-attachments/assets/f8854f4a-c9dc-45df-8657-8b6035d44540)
 Со клик на копчето Math problems ќе се отвори формата со математички задачи. ![image](https://github.com/user-attachments/assets/5a0264d9-c0c3-46a7-8139-f7eb2cd7546a)
 Тука има копчиња Easy, Medium, Hard со клик на некое од нив го избираме соодветното ниво во кое сакаме да решаваме. ![image](https://github.com/user-attachments/assets/a020ef3b-79f9-434b-a67e-6ed7c38c9fcf)
 Тука е кликнато копчето Easy и одбрана е операцијата множење, а исто така со клик на некое од копчињата Multiply, Divide, Add, Subtract ја избираме соодветната операција во која сакаме да решаваме. ![image](https://github.com/user-attachments/assets/5df2cdfb-6110-478a-9533-ab95eb3c390d)
 Во празното поле го внесуваме нашиот одговор и доколку го погодиме на екран се испишува Correct заедно со соодветниот број на обиди. ![image](https://github.com/user-attachments/assets/cd5ec182-85f5-4980-9218-0246946d31d5)
 Доколку кликниме на Medium i Add ќе се изгенерира задача од таков тип и доколку ставиме погрешен одговор на екран ќе се испише Incorrect и ќе се намали бројот на обиди. ![image](https://github.com/user-attachments/assets/94e1bdae-19d5-453d-b8fd-c84f5a811c1a)
Со клик на копчето Generate Question се генерираат различни задачи од типот на задачи кој сме го одбрале. А кога бројот ќе достигне 0 се генерира нова задача од соодветниот тип. ![image](https://github.com/user-attachments/assets/b7106cb8-4c7a-4435-b9ab-fc2372bcef7a). Тука имаме одбрано Hard level и операцијата делење. Во Easy спаѓаат задачи во интервалот од 1 до 10, во Medium од 10 до 50, а во Hard од 50 до 100.
![image](https://github.com/user-attachments/assets/8f5d08be-2a86-4e23-930b-b32e3f6d199b)

ОПИС НА РЕШЕНИЕТО НА ПРОБЛЕМОТ

Windows forms: Form2, MathTasks и ShapeTasks.

Класи: Shape и ShapeGame.

Form2: Тука имаме две копчиња btnForms и btnTasks private void btnForms_Click(object sender, EventArgs e). Кога ќе се кликне копчето се прикажува формата ShаpeTasks. ShapesTasks shapesTasks = new ShapesTasks();: Оваа линија создава нов објект од класата ShapesTasks. shapesTasks.Show();: Оваа линија ја прикажува формата ShapesTasks. private void btnTasks_Click(object sender, EventArgs e). Кога ќе се кликне копчето се прикажува формата MathTasks. MathTasks mathTasks = new MathTasks();: Оваа линија создава нов објект од формата MathTasks. mathTasks.Show();: Оваа линија ја прикажува формата MathTasks. Класата MathQuiz2: Претставува форма со две копчиња. Оваа структура му овозможува на корисникот да се движи помеѓу различни задачи (поврзани со форми и поврзани со математика) во рамките на апликацијата со кликање на соодветните копчиња.

MathTasks: { public partial class MathTasks : Form { private string currentDifficulty; private string currentOperation; private int trials = 5; private int correctAnswer;

    public MathTasks()
    {
        InitializeComponent();
    }
currentDifficulty: Го чува тековното ниво на тежина (лесно, средно, тешко). currentOperation: Го чува тековниот тип на математичка операција (собирање, одземање, множење, делење). trials: Бројот на преостанати обиди. correctAnswer: Точниот одговор на тековното прашање. Kопчиња за избор на тежина private void btnEasy_Click(object sender, EventArgs e) { currentDifficulty = "Easy"; MessageBox.Show("Easy difficulty selected."); }

    private void btnMedium_Click(object sender, EventArgs e)
    {
        currentDifficulty = "Medium";
        MessageBox.Show("Medium difficulty selected.");
    }

    private void btnHard_Click(object sender, EventArgs e)
    {
        currentDifficulty = "Hard";
        MessageBox.Show("Hard difficulty selected.");
    }
Овие методи го поставуваат тековното ниво на тежина и прикажуваат порака на корисникот. Kопчиња за избор на операција private void btnMultiply_Click(object sender, EventArgs e) { currentOperation = "Multiply"; GenerateQuestion(); }

    private void btnDivide_Click(object sender, EventArgs e)
    {
        currentOperation = "Divide";
        GenerateQuestion();
    }

    private void btnSubtract_Click(object sender, EventArgs e)
    {
        currentOperation = "Subtract";
        GenerateQuestion();
    }

    private void btnAdd_Click(object sender, EventArgs e)
    {
        currentOperation = "Add";
        GenerateQuestion();
    }
Овие методи го поставуваат тековниот тип на операција и генерираат ново прашање. private void btnGenerate_Click(object sender, EventArgs e) { GenerateQuestion(); }

    private void GenerateQuestion()
    {
        Random random = new Random();
        int num1, num2;
        switch (currentDifficulty)
        {
            case "Easy":
                num1 = random.Next(1, 10);
                num2 = random.Next(1, 10);
                break;
            case "Medium":
                num1 = random.Next(10, 50);
                num2 = random.Next(10, 50);
                break;
            case "Hard":
                num1 = random.Next(50, 100);
                num2 = random.Next(50, 100);
                break;
            default:
                num1 = random.Next(1, 10);
                num2 = random.Next(1, 10);
                break;
        }
        switch(currentOperation)
        {
            case "Multiply":
                correctAnswer = num1 * num2;
                lbQuestion.Text = $"How much is {num1} * {num2}?";
                break;
            case "Divide":
                correctAnswer = num1 / num2;
                lbQuestion.Text = $"How much is {num1} / {num2}?";
                break;
            case "Subtract":
                correctAnswer = num1 - num2;
                lbQuestion.Text = $"How much is {num1} - {num2}?";
                break;
            case "Add":
                correctAnswer = num1 + num2;
                lbQuestion.Text = $"How much is {num1} + {num2}?";
                break;
            default:
                correctAnswer = num1 * num2;
                lbQuestion.Text = $"How much is {num1} * {num2}?";
                break;
        }
        txtAnswer.Clear();
    }
GenerateQuestion(): Го генерира прашањето врз основа на тековното ниво на тежина и операција. Користи Random за да создаде два броја и поставува соодветно прашање и точен одговор. private void btnCheck_Click(object sender, EventArgs e) { int userAnswer; bool isNumeric = int.TryParse(txtAnswer.Text, out userAnswer); if(!isNumeric) { MessageBox.Show("Please enter a valid number."); return; } if(userAnswer==correctAnswer) { lbFeedBack.ForeColor = Color.Green; lbFeedBack.Text = "CORRECT"; } else { lbFeedBack.ForeColor = Color.Red; lbFeedBack.Text = "INCORRECT"; trials--; if (trials <= 0) { trials = 5; GenerateQuestion(); } } lbTrial.Text = $"Trials: {trials}"; } btnCheck_Click(): Го проверува корисничкиот одговор. Ако е точен, прикажува порака "CORRECT" со зелена боја. Ако е неточен, прикажува порака "INCORRECT" со црвена боја и намалува бројот на обиди. Кога обидите ќе достигнат 0, генерира ново прашање и ја ресетира бројката на обиди. private void MathTasks_Load(object sender, EventArgs e) { // Овде може да се додадат активности при вчитување на формата ако се потребни } } } MathTasks_Load(): Овој метод се извршува кога формата се вчитува. Може да се користи за иницијализација на некои вредности или контроли. Овој код овозможува создавање на интерактивна апликација за учење математика, која му овозможува на корисникот да избере ниво на тежина и тип на математичка операција, да решава задачи, и да добива повратни информации за точноста на одговорите.

Shape: Апстрактна класа Shape и неколку конкретни класи кои наследуваат од неа, како Circle, Square, Triangle, Pentagon, Hexagon, и Rhombus. Секој облик има свој начин на цртање користејќи Graphics објект и Rectangle кој го дефинира просторот во кој обликот ќе биде нацртан. Апстрактна класа Shape public abstract class Shape { public string Name { get; set; }

public Shape (string name)
{
    Name = name;
}

public abstract void Draw (Graphics g, Rectangle r);
} Name: Го чува името на обликот. Shape(конструктор): Го иницијализира името на обликот. Draw: Апстрактен метод кој мора да биде имплементиран во секоја подкласа за да го дефинира начинот на цртање на обликот. Класа Circle public class Circle : Shape { public Circle() : base("Circle") { }

public override void Draw(Graphics g, Rectangle r)
{
    g.FillEllipse(Brushes.Blue, r);
}
} Конструктор: Го поставува името на обликот на "Circle". Draw: Го црта кругот користејќи син Brush. Класа Square public class Square : Shape { public Square() : base("Square") { }

public override void Draw(Graphics g, Rectangle r)
{
    int size = Math.Min(r.Width, r.Height);
    int x = r.Left + (r.Width - size) / 2;
    int y = r.Top + (r.Height - size) / 2;

    g.FillRectangle(Brushes.Red, x, y, size, size);
}
} Конструктор: Го поставува името на обликот на "Square". Draw: Го црта квадратот со црвен Brush, прилагодувајќи го за да биде центриран во правоаголникот. Класа Triangle public class Triangle : Shape { public Triangle() : base("Triangle") { }

public override void Draw(Graphics g, Rectangle r)
{
    Point[] points =
    {
        new Point(r.Left + r.Width / 2, r.Top),
        new Point(r.Left, r.Bottom),
        new Point(r.Right, r.Bottom)
    };

    g.FillPolygon(Brushes.Green, points);
}
} Конструктор: Го поставува името на обликот на "Triangle". Draw: Го црта триаголникот користејќи зелен Brush. Класа Pentagon public class Pentagon : Shape { public Pentagon() : base("Pentagon") { }

public override void Draw(Graphics g, Rectangle r)
{
    Point[] points =
    {
        new Point(r.Left + r.Width / 2, r.Top),
        new Point(r.Right, r.Top + r.Height / 3),
        new Point(r.Right - r.Width / 4, r.Bottom),
        new Point(r.Left + r.Width / 4, r.Bottom),
        new Point(r.Left, r.Top + r.Height / 3)
    };
    g.FillPolygon(Brushes.Purple, points);
}
} Конструктор: Го поставува името на обликот на "Pentagon". Draw: Го црта петаголот користејќи виолетов Brush. Класа Hexagon public class Hexagon : Shape { public Hexagon() : base("Hexagon") { }

public override void Draw(Graphics g, Rectangle r)
{
    int width = r.Width;
    int height = r.Height;
    Point[] points =
    {
        new Point(r.Left + width / 4, r.Top),
        new Point(r.Right - width / 4, r.Top),
        new Point(r.Right, r.Top + height / 2),
        new Point(r.Right - width / 4, r.Bottom),
        new Point(r.Left + width / 4, r.Bottom),
        new Point(r.Left, r.Top + height / 2)
    };
    g.FillPolygon(Brushes.Orange, points);
}
} Конструктор: Го поставува името на обликот на "Hexagon". Draw: Го црта шестоаголот користејќи портокалов Brush. Класа Rhombus public class Rhombus : Shape { public Rhombus() : base("Rhombus") { }

public override void Draw(Graphics g, Rectangle r)
{
    int width = r.Width;
    int height = r.Height;
    Point[] points =
    {
        new Point(r.Left + width / 2, r.Top),
        new Point(r.Right, r.Top + height / 2),
        new Point(r.Left + width / 2, r.Bottom),
        new Point(r.Left, r.Top + height / 2)
    };
    g.FillPolygon(Brushes.Pink, points);
}
} Конструктор: Го поставува името на обликот на "Rhombus". Draw: Го црта ромбот користејќи розов Brush. Заклучок Сите овие класи наследуваат од апстрактната класа Shape и ја имплементираат методата Draw за да го дефинираат начинот на кој секој облик ќе биде нацртан. Овој пристап овозможува лесно додавање нови облици и едноставно користење на полиморфизмот за да се цртаат различни облици без да се менува основниот код.

ShapesGame: класа ShapeGame, која управува со играта каде корисникот треба да ги погоди имињата на случајно генерираните облици. Класата има неколку клучни функции и променливи кои го олеснуваат управувањето со играта. Тука се чуваат Приватни променливи: Random random: Случаен генератор кој се користи за генерирање на случаен облик. List shapes: Листа од различни објекти од типот Shape, кои претставуваат различни геометриски облици (круг, квадрат, триаголник, пентагон, хексагон и ромбус). Јавни променливи: int Tries: Број на обиди на корисникот за да го погоди обликот. Се иницијализира на 3. Shape CurrentShape: Објект од типот Shape кој го претставува тековниот облик што треба да се погоди.

ShapesTasks: Овој код создава форма наречена ShapesTasks која прикажува облик и овозможува на корисникот да го погоди името на обликот. Играта има неколку обиди и секој обид го ажурира екранот. Тука се чуваат Приватни променливи: currentDifficulty: Стринг кој ја чува тековната тежина (не се користи во дадениот код). Trials: Целобројна променлива за бројот на обиди (не се користи во дадениот код). correctAnswer: Стринг кој ја чува точниот одговор (не се користи во дадениот код). game: Објект од класата ShapeGame која управува со логиката на играта.
