//Prova ADS - Guilherme Gabriel Barros - ra: 190975 

using System;

namespace Pato
{
    class Program
    {
        static void Main(string[] args)
        {
            Pato pt = new Pato_Ruivo();

            Console.WriteLine(pt.mostrar());
            Console.WriteLine(pt.nadar());
            Console.WriteLine(pt.comportamento_pato());

            pt.setComportamento(new Voar_Foguete());

            Console.WriteLine(pt.comportamento_pato());
        }
    }

    public interface Padrao_Voaveis
    {

        String voar();

        double getVelocidade();

    }

    public abstract class Pato
    {

        protected Padrao_Voaveis comportamento_pato;

        abstract String mostrar();

        public String nadar()
        {
            return "Pato Nadando.";
        }

        public void setComportamento(Padrao_Voaveis padrao)
        {
            comportamento_pato = padrao;
        }

        public String comportamento_pato()
        {
            return comportamento_pato.voar();
        }
    }


    public interface Padrao_Grasnar
    {

        String grasnar();

    }


    public class Voaveis_Asa : Padrao_Voaveis
    {

        private double velocidade;

        public Voaveis_Asa()
        {
            velocidade = 10;
        }

        public String voar()
        {
            return "Voando como um pássaro que voa. Velocidade: "
                    + getVelocidade();
        }

        public double getVelocidade()
        {
            return velocidade;
        }

    }

    public class Voar_Foguete : Padrao_Voaveis
    {


        private double velocidade;

        public Voar_Foguete()
        {
            velocidade = 1000;
        }

        public String voar()
        {
            return "Voando como um foguete. Velocidade: " + getVelocidade();
        }

        public double getVelocidade()
        {
            return velocidade;
        }
    }


    public class Pato_Bravo : Pato
    {

        public Pato_Bravo()
        {
            setComportamento(new Voaveis_Asa());
        }

        public String mostrar()
        {
            return "Eu sou o Pato Bravo.";
        }

        public String grasnar()
        {
            return "Que-Que. Grrrrrrrrr.";
        }

    }

    public class Pato_Bravo : Padrao_Grasnarto
    {

        public Pato_Bravo()
        {
            setComportamento(new Voaveis_Asa());
        }

        public String mostrar()
        {
            return "Eu sou o Pato Bravo.";
        }

        public String grasnar()
        {
            return "Que-Que. Grrrrrrrrr.";
        }

    }
    public class Pato_Ruivo : Pato
    {

        public Pato_Ruivo()
        {
            setComportamento(new Voaveis_Asa());
        }

        public String mostrar()
        {
            return "Eu sou o Pato Ruivo.";
        }

        public String grasnar()
        {
            // TODO Auto-generated method stub
            return "Que-Que.";

        }

    }

    public class Pato_Ruivo : Padrao_Grasnar
    {

        public Pato_Ruivo()
        {
            setComportamento(new Voaveis_Asa());
        }

        public String mostrar()
        {
            return "Eu sou o Pato Ruivo.";
        }

        public String grasnar()
        {
            // TODO Auto-generated method stub
            return "Que-Que.";

        }

    }

    public class Pato_Borracha : Pato
    {

        public Pato_Borracha()
        {
            setComportamento(new Nao_Voa());
        }

        public String mostrar()
        {
            return "Olá, eu sou de Boarracha.";
        }

    }

    public class Nao_Voa : Padrao_Voaveis
    {


        public Nao_Voa()
        {

        }

        public String voar()
        {
            return "Esse pato não Voa. Velocidade: " + getVelocidade();
        }

        public double getVelocidade()
        {
            return 0;
        }

    }

    public class Apito : Padrao_Grasnar
    {

        public String grasnar()
        {
            return "Queeeeee";
        }
    }


}

